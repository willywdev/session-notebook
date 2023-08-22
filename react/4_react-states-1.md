# React States I

- Problem bei dynamischen Variablen: Werte aktualisieren sich nicht in der Anzeige innerhalb von Komponenten.
- Lösung: Verwendung von React States, um dieses Problem anzugehen.

## Beispiel ohne React States:

```jsx
function Counter() {
  let count = 0;

  function handleClick() {
    count = count + 1;
    console.log("Klick", count);
  }

  return (
    <button onClick={handleClick}>
      Du hast diesen Button {count}-mal geklickt
    </button>
  );
  // {count} ändert sich nicht in der Anzeige? Grund: React Rerender-Zyklus
}
```

## React Rerender-Zyklus

- React bestimmt automatisch, wann Komponenten aktualisiert werden.
- Wir müssen React mitteilen, wann eine Komponentenfunktion erneut aufgerufen werden soll (Rerender).
- Dies geschieht mithilfe von Updater-Funktionen, auch bekannt als **React States**.
- Initialer Render zeigt statischen "Snapshot" der Komponente.
- Trigger (wie Updater-Funktion) löst Rerender aus, erstellt neuen "Snapshot".
- React vergleicht beide "Snapshots" und aktualisiert nur geänderte Teile.

## React States

- React verwaltet Zustände mit **React States**.
- `useState` ist ein Hook in React zur Zustandsverwaltung in funktionalen Komponenten.
- Die meisten Hooks beginnen mit `use`.
- `useState` gibt ein Array zurück: Zustandsvariable + dazugehörige Updater-Funktion.
- Zustandsvariable speichert aktuellen Zustand, Updater-Funktion aktualisiert Zustand.
- Bei dynamischen Werten, die sich ändern können, verwenden wir **States**.
- Zustandsmanagement ist entscheidend für reaktive und interaktive Benutzeroberflächen.
- `useState` hat Syntax: `const [state, setState] = useState(initialValue);`
- Zustände helfen, den "Single Source of Truth" in React-Anwendungen zu erreichen.
- Verwendung von Zuständen macht den Code einfacher zu verstehen und zu warten.
- Zustände ermöglichen es uns, auf Benutzerinteraktionen in Echtzeit zu reagieren.

## Verbessertes Beispiel mit `useState`:

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1); // Trigger für Rerender
    console.log("Klick", count);
  }

  return (
    <button onClick={handleClick}>
      Du hast den Button {count}-mal geklickt.
    </button>
  );
}
```

Durch Verwendung von `useState` wird der Zähler korrekt verwaltet und in der Anzeige aktualisiert, sobald sich der Wert ändert.
