# JavaScript Functions II

## Die `return` Anweisung

Die `return` Anweisung wird verwendet, um den Wert oder Ausdruck, der in der Funktion berechnet wurde, zurückzugeben. Sobald die `return` Anweisung ausgeführt wird, wird die Funktion beendet und der Rückgabewert wird an den Ort zurückgegeben, von dem aus die Funktion aufgerufen wurde.

Beispiel:

```javascript
function add3Numbers(a, b, c) {
  return a + b + c;
}

const result = add3Numbers(1, 2, 3);
console.log(result); // Gibt 6 aus
```

## Arrow Function Expression

Arrow Functions sind eine verkürzte und kompaktere Syntax für die Definition von Funktionen. Anstatt das `function`-Keyword zu verwenden, werden Pfeil (`=>`) und runde Klammern verwendet.

Beispiel:

```javascript
const add2Numbers = (a, b) => {
  return a + b;
};

const result = add2Numbers(3, 5);
console.log(result); // Gibt 8 aus
```

Wenn die Funktion nur einen Ausdruck enthält, kann die geschweifte Klammer und das `return`-Keyword weggelassen werden.

Beispiel:

```javascript
const add2Numbers = (a, b) => a + b;

const result = add2Numbers(3, 5);
console.log(result); // Gibt 8 aus
```

## Anonyme Funktionen

Eine anonyme Funktion ist eine Funktion ohne Namen. Arrow Functions eignen sich besonders gut für die Verwendung als anonyme Funktionen.

Beispiel:

```javascript
const printMessage = (message) => {
  console.log(message);
};

printMessage("Hello!"); // Gibt "Hello!" in der Konsole aus
```

Arrow Functions werden häufig verwendet, wenn Funktionen als Argumente an andere Funktionen übergeben werden, z. B. bei Array-Methoden wie `map`, `filter`, `forEach`, usw.
