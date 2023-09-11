# React Data Fetching

- customHooks, um `fetch` , `async / await` und `useEffect()` zu vereinfachen: **SWR** oder **React Query**
- Library to fetch data: Axios, GraphQL

## Custom Hook `useFetch`:

```jsx
function useFetch(url) {
  const [data, setData] = useState();

  useEffect(() => {
    async function startFetching() {
      const response = await fetch(url);
      const newData = await response.json();
      setData(newData);
    }
    startFetching();
  }, [url]);
  return data;
}
```

## customHook: SWR by Vercel

- Interval, Cleanup Funktion, Data Cacheing
- Fetching in Intervals to get Data earlier, than the user requests
- Cacheing of the Data, so even when reloading the page, the data is there
- Fetcher Function is needed

```jsx
import useSWR from "swr";

const fetcher = (...args) => fetch(...args).then((res) => res.json());
// ^ --- Fetcher function (SWR Docs)

export default function Joke() {
	const { data, error, isLoading, isValidating } =
		useSWR("URL", fetcher);

	if(error) {
		return <h1>Something went wrong ...</h1>
	}

	if (isLoading) {
		return <h1>Loading ...</h1>;
	}

	return (...)
}
```

- Much faster, cleaner and in sync between data. Also it caches data
- useSWR is using cached data, but also validates the data by fetching the data again in the Background

## Make fetcher function global

```jsx
// --- in _app.js:
import { SWRConfig } from "swr";

const fetcher = (...args) => fetch(...args).then((res) => res.json())

export default function App({Component, pageProps}) {
	return (
		<>
			<GlobalStyle />
			<SWRConfig value=({ fetcher })>
				<Component {...pageProps} />
			</SWRConfig>
		</>
	)
}
```

-> Don't need to provide second argument "fetcher" to `useSWR()`

## Update / Add data to existing data

```js
const [jokesInfo, setJokesInfo] = useState([]);

// nullish coalescing
const info = jokesInfo.find((info) => info.id === id) ?? {
	isFunny: false,
};
const { isFunny } = info;

...

<span>{ isFunny ? ":D" : ":(" }</span>

...
function handleToggleFunny(id) {
	setJokesInfo((jokesInfo) => {
		const info = jokesInfo.find((info) => info.id === id);
		if (info) {
			return jokesInfo.map(info => info.id === id ? {...info, isFunny: !isFunny} : info)
		}

		return [...jokesInfo, {id, isFunny: true}];
	})
}

<button onClick={() => handleToggleFunny(id)} >{isFunny ? "This is not funny" : "This is funny"}</button>
```
