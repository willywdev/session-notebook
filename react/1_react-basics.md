# React Basics

## Geschichte - Probleme bevor React:

- Last der Website zu groß
- Website viel zu komplex geworden
- Problematik: Synchronität zwischen mehreren Bereichen
- Unterschiedliche Teams arbeiten an verschiedenen Bereichen (Komponenten)
- Lösung von Facebook war: React
- Das erste was mit React gebaut wurde, war Instagram

[![Video](https://img.youtube.com/vi/8pDqJVdNa44/maxresdefault.jpg)](https://www.youtube.com/watch?v=8pDqJVdNa44&pp=ygUOSG9uZXlwb3QgcmVhY3Q%3D)

## React Basics

- Wird unteranderem über NPM installiert
- React = Library
- React API = React + ReactDOM
- Erzeugt eigenes DOM (Virtual DOM)
- verwendet JSX (JavaScript Syntax Extension)
  - HTML CSS und JS in einer Syntax
- Schreiben Funktionen und in diesen Funktionen beschreiben wir, was wir haben wollen

```javascript
function Headline() {
  return <h1>Hello World</h1>;
}
```

- Diese Funktionen wandelt den Code in JavaScript um. z.B. createElement(), append(), classList.add(), ....
- Es wird nur das im DOM ausgetauscht, was verändert wird. z.B. bei einem Counter wird nur die Zahl gewechselt, anstatt dem gesamten HTML Skelett

## React Praxis

- In die `.render()` Funktion darf nur 1 Parameter übergeben werden. Das ist in meisten Fällen ein `<div>` als Eltern Element, welches das JSX umschließt.
- index.html: `<div id="root"></div>` <- Das ist die Einfügestelle für React.
- index.js:

```jsx
import { createRoot } from "react-dom/client";

const rootElement = document.querySelector("#root");

// Unser root Element zu einem React Root Element machen:
const root = createRoot(rootElement);

root.render(
  <div>
    <h1 id="greeting">Hello World</h1>
    <p className="intro">I am rendered by React</p>
    <label htmlFor="password">Password:</label>
  </div>
);
// Das ist kein HTML, sondern JSX
```

- Man kann auch dynamische Werte benutzen mit Variablen:

```jsx
const name = "Willy";

root.render(<h1>Hello {name}</h1>);
```

- Man denkt in React, wenn man in Komponenten denkt

## Komponenten Praxis

```jsx
function Greeting() {
  const name = "Willy";
  return <h1 id="greeting">Hello {name}</h1>;
}

function Button() {
  return <button>Click</button>;
}

root.render(
  <div>
    <Greeting />
    <Button />
    <Button />
    <Button />
    // Komponenten können mehrfach verwendet werden
  </div>
);
```

## Doppelte `<div>` umgehen:

```jsx
root.render(
  <>
    {" "}
    // Fragment: React rendert die Elemente direkt im #root-div
    <Greeting />
    <Button />
  </>
);
```

## Ordner Struktur:

```
public
	--index.html
	--style.css
src
	components
		--Greeting.js
	--App.js
	--index.js
```

**App.js**

```jsx
import Greeting from "./components/Greeting";

export default function App() {
	return (
		<div>
			<Greeting />
			<p className="greeting">Created by React</p>
		</div>
	)
}

function Greeting() {
	...
}
```

**index.js**

```jsx
import { createRoot } from "react-dom/client";
import App from "./App";

const rootElement = document.querySelector("#root");
const root = createRoot(rootElement);

root.render(<App />);
```

**Greeting.js**

```jsx
export default function Greeting() {
  return <h1>Hello World!</h1>;
}
```
