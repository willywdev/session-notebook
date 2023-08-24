# React States 2

Wie verwendet man Formulare in React?
Wie kann man States zwischen Komponenten teilen?
-> Lifting State up

`onSubmit` -> Event Handler für Submit
`autoComplete="off"` um die Autovervollständigung abzuschalten

`htmlFor` als Ersatz für das in HTML vorkommende HTML `for`

## Lifting State Up

- useState() in globaler Komponente benutzen bzw. in Eltern Komponenten
- Variable und Setter Funktion als Props übergeben:

```jsx
export default function App() {
  const [searchTerm, setSearchTerm] = useState("");
  // ^ Lifting State Up, indem man es in einer Eltern Komponente 					 deklariert
  function handleSearch(term) {
    setSearchTerm(term);
  }
  return (
    <main>
      <h1>Search</h1>
      <SearchForm searchTerm={searchTerm} onSearch={handleSearch} />
      // ^ State als props übergeben, um diese in den Komponenten zu
      manipulieren
      <SearchResults searchTerm={searchTerm} />
    </main>
  );
}
```

## Controlled Input

```jsx
export default function SearchForm({ searchTerm, onSearch }) {
  const [searchFieldValue, setSearchFieldValue] = useState("");

  function handleSubmit(event) {
    event.preventDefault();
    onSearch(searchFieldValue);
  }

  return (
    <>
      <form onSubmit={handleSubmit} autoComplete="off">
        <label htmlFor="searchTerm">Search term:</label>
        <input
          name="searchTerm"
          id="searchTerm"
          type="text"
          value={searchFieldValue}
          onChange={(event) => setSearchFieldValue(event.target.value)}
        />
        // ^ Controlled Input. Man arbeitet gezielt an dem Element, aus dem man
        die Werte übergeben möchte
        <button>
          <span role="img" aria-label="search icon">
            🔍
          </span>{" "}
          Search
        </button>
      </form>
      <h2>
        {searchTerm
          ? `You searched for "${searchTerm}"`
          : "Please enter a search term"}
      </h2>
    </>
  );
}
```

## Uncontrolled Input

```jsx
export default function SearchForm({ searchTerm, onSearch }) {
  function handleSubmit(event) {
    event.preventDefault();
    const formElements = event.target;
    onSearch(formElements.searchTerm.value);
    // ^ Man arbeitet mit dem gesamten Form-Element um seine Werte zu extrahieren und sie dann weiterzugeben
  }

  return (
    <>
      <form onSubmit={handleSubmit} autoComplete="off">
        <label htmlFor="searchTerm">Search term:</label>
        <input name="searchTerm" id="searchTerm" type="text" />
        <button>
          <span role="img" aria-label="search icon">
            🔍
          </span>{" "}
          Search
        </button>
      </form>
      <h2>
        {searchTerm
          ? `You searched for "${searchTerm}"`
          : "Please enter a search term"}
      </h2>
    </>
  );
}
```
