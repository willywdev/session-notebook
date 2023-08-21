# React Nesting

## Eigene React App erstellen mit `create-react-app`

- Nicht relevant sobald man mit Next.js arbeitet oder mit Vite
- Vorgefertigtes Template mit einem React Boilerplate
- Installiert react, react-dom, react-scripts und cra-template
- Live Preview Extension funktioniert nicht mehr mit React. Deswegen `npm start` oder `npm run dev` (oder mehr in der package.json)

```bash
npx create-react-app my-app
cd my-app
npm start
```

- Meist muss man Dateien löschen, die man nicht mehr braucht. Aber man kriegt auch Templates zu Dateien, die man braucht z.B. `.gitignore`

## JSX Fragment

```jsx
function Animal({ emoji, name }) {
  return (
    // Ein Fragment. Quasi ein leeres HTML Element
    <>
      <h2></h2>
      <p></p>
    </>
  );
}
```

- Wird nicht von react gerendert
- Mehrere Elemente können in einem Fragment gewrappet werden
- Dieses Element findet man nicht im DOM

## Children Komponente

- Besondere Komponente in react
- Children Prop
- Alles was zwischen Opening und Closing geschrieben wird, wird von react zusammengefasst und nennt sich Children
- `children` ist festgelegt von react und muss immer so heißen

```jsx
function Animal(...) {
	return (
		...
		// --- Children Prop --- \\
		<Button>{name}</Button>
	)
}

// ----------- Children Prop -------- \\
function Button({ children }) {
	return (
		<button type="button" className="button">Adopt {children}</button>
	)
}
```

- `children` beinhaltet alles was zwischen Opening und Closing Tag steht.
- `children` ist ein Array

## Komponenten und Funktionen auslagern

- Macht den Code übersichtlicher & erleichtert Debugging
- export & import
- Neuen Ordner erstellen `components`
- Innerhalb `components` kommen die Komponenten, auch als Ordner erstellt
- Bei Komponenten immer `export default`
- Bei react brauchen wir beim importieren nicht mehr die Dateiendung `.js`, weil das beim Builden gebundelt wird. Der Bundler kann den Pfad richtig auflösen
- Bei react können wir auch CSS Dateien importieren
