# JavaScript Callback Functions

## Callback Functions

- Eine Callback-Funktion ist eine Funktion, die von einer anderen Funktion (Higher Order Function) aufgerufen wird.
- Callback-Funktionen werden als Argumente an die Higher Order Function übergeben und von dieser später aufgerufen.
- Eine Higher Order Function ist eine Funktion, die andere Funktionen entgegennimmt oder sie als Rückgabewert zurückgibt.

## Beispiel mit EventListener

- Der EventListener ist eine typische Higher Order Function, die eine Callback-Funktion entgegennimmt, die aufgerufen wird, wenn das Ereignis eintritt.
- Bisher haben wir anonyme Arrow Functions als Callback-Funktionen verwendet:

```javascript
saveButton.addEventListener("click", () => {
  console.log("saved");
});
```

## Named Functions als Callbacks

- Es ist auch möglich, benannte Funktionen als Callbacks zu verwenden:

```javascript
function handleCancel() {
  console.log("canceled");
}

cancelButton.addEventListener("click", handleCancel);
```

- Wenn benannte Funktionen verwendet werden, dürfen keine Klammern hinter den Funktionsnamen geschrieben werden, da die Funktion erst vom EventListener aufgerufen wird.

## Komponenten

- Komponenten sind Funktionen, die ein DOM-Element zurückgeben und zur Erstellung wiederverwendbarer Elemente dienen.
- Zum Beispiel können wir eine Komponente für die Erstellung von Buttons erstellen:

```javascript
function Button(text, onClick) {
  const buttonElement = document.createElement("button");
  buttonElement.textContent = text;
  buttonElement.addEventListener("click", onClick);
  return buttonElement;
}
```

- Diese Komponente kann dann verwendet werden, um Buttons mit verschiedenen Texten und Funktionen zu erstellen:

```javascript
const alertButton = Button("show message", () => {
  // Hier kommt der Code für den Klick-Event
});
```
