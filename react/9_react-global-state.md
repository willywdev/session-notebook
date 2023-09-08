# React Global State

- **"So weit unten wie möglich, so weit oben wie nötig"**
- Lifting up State -> ein State der von mehreren Komponenten genutzt wird. Dafür wird der State in das jeweils höhere gemeinsame Elternkomponent gehoben und dann als Prop weitergegeben
- In der \_app.js findet man den return von `<Component {...pageProps} />`.
  Dies steht für alle Components / Pages
- Local State vs Uplifted State vs Global State
- Wenn wir ein State haben, der auf mehreren Seiten verfügbar sein soll, muss er auf der globalen Ebene erstellt werden (bei next.js: \_app.js)

- Nebenbei: Layout Komponente mit Header, Main, Footer

## Global State

```jsx
const initialAnimals = [
	{
		count: 0,
		name: "Cats",
		id: 1
	},
	{
		count: 0,
		name: "Dogs",
		id: 2
	},
	{
		count: 0,
		name: "Sheeps",
		id: 3
	},
	{
		count: 0,
		name: "Dragons",
		id: 4
	}
]

export default function App({ Component, pageProps }) {
	const [animals, setAnimals] = useState();

	function handleAdd(animalId) {
		setAnimals(animals.map((animal) => {
			if(animal.id === animalId) {
				return {...animal, count: animal.count + 1}
			} else {
				return animal;
			}
		}))
	}

	function handleSubtract(animalId) {
		setAnimals(animals.map((animal) => {
			if(animal.id === animalId) {
				return {...animal, count: Math.max(0, animal.count - 1)}
			} else {
				return animal;
			}
		}))
	}

	const animalCounts = animals.map((animal) => {
		return animal.count;
	});
	const countSum = animalCounts.reduce((a, b) => {
		return a + b;
	});
	const countAverage = countSum / animals.length;
	const dragonCount = animals.find((animal) => {
		return animal.name === "Dragons";
	}).count;

	return (
		<GlobalStyle />
		<Layout dragonCount={dragonCount} countSum={countSum}>
			<Component {...pageProps} animals={animals} 								handleAdd={handleAdd} handleSubtract={handleSubtract} 						dragonCount={dragonCount} countSum={countSum} 								countAverage={countAverage} />
		</Layout>
	)
}
```

**Prop drilling**: Props durchgeben von unten nach oben. Fehleranfällig. Bad DX.

## React Library for Global States: Zustand

~[zustand on GitHub](https://github.com/pmndrs/zustand)~

- Prop drilling not required anymore
