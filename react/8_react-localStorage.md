# React LocalStorage & SessionStorage

- LocalStorage und SessionStorage sind Teil der Web Storage API
- LocalStorage = Bleibt vorhanden, bis Cache gelöscht wird
- SessionStorage = Bleibt vorhanden, solange der Browsertab geöffnet ist
- Sinnvoll für Profilinformationen oder für Usereinträge die noch nicht abgesendet / gespeichert wurden
- Daten werden in Key-Value Pairs gespeichert
- `getItem` und `setItem` , um Daten zu speichern und zu holen

```js
// --- Vanilla --- \\
localStorage.setItem("theme", "light");
localStorage.getItem("theme");

localStorage.removeItem("theme");
localStorage.clear();
```

- Daten hinzufügen geht nur, wenn man den ursprünglichen Key überschreibt. Will man also Daten hinzufügen, muss man die alten Daten immer mit hinzufügen
- Komplexe Datentypen können nicht im Storage gespeichert werden, ein Umweg:

```js
// --- Vanilla --- \\
// Aus einem Object ein String machen:
localStorage.setItem("settings", JSON.stringify(Object));

// Aus einem String wieder ein Object machen:
JSON.parse(localStorage.getItem("settings"));
```

## Verwenden von localStorage in React mit einer Library

- Library: `use-local-storage-state`
- Installierbar über npm
- Alles was man sonst für localStorage brauchte, wird nun von der Library erledigt
- Ist ein Custom Hook

```jsx
import useLocalStorageState from "use-local-storage-state";
```

- Wird oft verwendet, um `useState()` auszutauschen und somit die Daten im `localStorage` zu speichern

```jsx
const [todos, setTodos] = useLocalStorageState("todos", { defaultValue: [] });
```
