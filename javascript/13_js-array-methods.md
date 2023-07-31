# JavaScript Array Methods

## forEach

- `forEach` wird verwendet, um eine Aktion für jedes einzelne Element eines Arrays auszuführen.
- Einzige Funktion ist das Ausführen des Callbacks für jedes Element.
- Es gibt keine Rückgabe (void), daher kann das ursprüngliche Array nicht manipuliert werden.

```javascript
const colors = ["blue", "red", "green", "purple"];
colors.forEach((color) => {
  console.log(color);
});
```

## map

- `map` wird verwendet, um ein neues Array zu erstellen, indem jede Position des ursprünglichen Arrays manipuliert wird.
- Die Funktion gibt ein neues Array zurück, das die gleiche Anzahl von Elementen wie das ursprüngliche Array hat.

```javascript
const colorsUppercase = colors.map((color) => {
  return color.toUpperCase();
});
```

## filter

- `filter` wird verwendet, um ein neues Array zu erstellen, indem nur bestimmte Elemente aus dem ursprünglichen Array ausgewählt werden.
- Die Funktion gibt ein neues Array zurück, dessen Größe variabel sein kann, abhängig von der Anzahl der Elemente, die den Filterbedingungen entsprechen.

```javascript
const animalsStartWithF = animals.filter((animal) => {
  return animal.startsWith("F");
});
```
