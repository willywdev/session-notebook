# React useEffect & fetch

- React Daten sind voraussagbar
- Fetch Daten sind Side Effects und nicht voraussagbar (mal Daten, mal Error, ...)
  -> Funktionen werden 'unpure'
- React stellt uns dafür Escape Catches zur Verfügung
- Wann immer sich ein State ändert, wird die Komponente neu gerendert -> Endlosschleife bei z.B. Fetch-API

## Hook: .useEffect()

- Hier werden Side Effects geschrieben
- Wird immer gefeuert, wenn etwas neues gerendert wird
- Man kann auch festlegen, wann `useEffect` feuert
- Fetch kann zu Endlosschleifen führen (!), weil die Komponente neugeladen wird und dann wieder von vorne anfängt -> Deswegen brauchen wir `useEffect()`
- Side Effects dürfen niemals im Render selbst ausgelöst werden, sondern erst nach dem Rendern
- Beim fetchen braucht man auch immer ein useState()

```jsx
import { useState, useEffect } from "react";

export default function Joke() {
  const [joke, setJoke] = useState("");
  const [id, setId] = useState(0);

  useEffect(() => {
    async function startFetching() {
      const response = await fetch(`URL/${id}`);
      const fetchedJoke = await response.json();

      setJoke(fetchedJoke);
    }
  }, [id]);
  // ^ Dependancy Array: Wann soll der useEffect ausgeführt werden?
  // [] = Nach dem ersten Laden der Komponente
  // [id] = Nach dem ersten Laden der Komponente UND wenn sich der State 				von id ändert

  if (!joke) {
    return null;
  }

  return (
    <>
      <h1>{joke}</h1>
      <button type="button" onClick={() => setId(joke.nextId)}>
        Next Joke
      </button>
    </>
  );
}
```

- useEffect nimmt zwei Parameter an: Callback-Funktion und ein Dependency Array
  - Dependency Array: Was sind die Bedingungen die erfüllt sein müssen, damit der Code feuert?
  - Leer = useEffect wird nur einmal gefeuert: Wenn die Seite geladen wurde
