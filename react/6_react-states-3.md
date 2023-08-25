# React States 3

- Wenn ein State sonst woanders nicht benötigt wird, sollte dieser State so tief in die Komponente wie möglich
- setFunction soll in eine Handler Funktion gewrappet werden, damit die Logik beim State bleibt und nicht in die Komponenten gegeben wird. Außerdem spart man sich so die State Variable mit zu übergeben
- Gibt man die setState Variable so rüber, ist es Bad Practice

## Manage von CRUD Operations

- Eigentlich typische Datenbankoperationen, aber bei States
- Hier sieht man **READ**, indem wir über das Array mappen und dieses rendern

```jsx
import {useState} from "react";

const initialPeople = [
	{
		id: "1",
		name: "Alex"
	},
	{
		id: "2",
		name: "Max"
	},
	{
		id: "3",
		name: "Jenny"
	}
]

export default function App() {
	const [people, setPeople] = useState(initialPeople);

	return (
		<>
			<h1>React State 3</h1>
			<form>...</form> // Input Feld wo wir die Daten bekommen

			<ul>
				{people.map((person) => {
					return (
						...
					)
				})
			</ul>
		</>
	)

}
```

### Adden eines Objects zu einem Array (CREATE)

```jsx
// 1. Spread old data into new Data
// 2. Put new Object after or before
// -- 2.1 Generate unique Key dynamically (UUID)
// -------- Don't use UUID Generator from Crypto API: Better use Nano ID

setPeople([...people, { id: uid(), name: data.name }]);
```

- `.shift` , `.unshift` , usw. funktionieren nicht, da React nicht weiß, dass es Rerendern soll. Es arbeitet nicht mit dem State, da es den selben Speicher anspricht und kein neues Array erstellt wird
- Deshalb benutzt man `...spread` und ein angehängtes Objekt

### DELETE

```jsx
{people.map((person) => {
	<li key={person.id}>
		{person.name} - id: {person.id}{" "}
		<button type="button" onClick={() => {
			const newPeopleArray = people.filter((_person) => {
										return _person.id !== person.id;
									})
			setPeople(newPeopleArray);
		}}
		</button>
	</li>
})}
```

- `pop` und `splice` funktionieren nicht, genau wie beim Adden die anderen Array Methoden, da kein neues Array erstellt wird und die gleiche Referenz besteht
- Deshalb benutzt man `.filter()`

### UPDATE

-> `.map()`
