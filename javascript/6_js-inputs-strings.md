# JavaScript Inputs und Strings

## JavaScript Inputs

Bei HTML-Formularen wird der Event Listener auf das `<form>`-Element gesetzt, _nicht_ auf den Submit-Button oder die Input-Elemente.

```javascript
const form = document.querySelector("form");

form.addEventListener("submit", (event) => {
  event.preventDefault();
  // Code to handle form submission goes here
});
```

Das `submit`-Event eines Formulars führt standardmäßig dazu, dass die Seite neu geladen wird. Mit `event.preventDefault();` wird das Standardverhalten verhindert, um die eingegebenen Daten nicht zu verlieren.

Um die eingegebenen Daten aus den Textfeldern zu erhalten, kann man auf die `value`-Eigenschaft der Input-Elemente zugreifen.

Beispiel:

```javascript
const usernameInput = document.getElementById("username");
const passwordInput = document.getElementById("password");

const username = usernameInput.value;
const password = passwordInput.value;
```

## Strings

Strings sind Zeichenketten und werden in JavaScript mit `" "` oder `' '` oder ` ` ` umschlossen.

String-Konkatenation (Zusammenfügen) wird mit dem `+`-Operator durchgeführt.

Beispiel:

```javascript
const firstName = "John";
const lastName = "Doe";

const fullName = firstName + " " + lastName;
```

Alternativ kann man auch Template Literals verwenden, die mit `` ` `` umschlossen werden. Innerhalb der Template Literals können Variablen mit `${}` eingefügt werden.

Beispiel:

```javascript
const firstName = "John";
const lastName = "Doe";

const fullName = `${firstName} ${lastName}`;
```

Zeilenumbrüche und mehrere Leerzeichen innerhalb von Template Literals werden nicht gerendert, was sie sehr nützlich für das Erstellen von formatiertem Text und mehrzeiligen Zeichenketten macht.

Um einen String in eine Zahl (Number) umzuwandeln, kann man das `+` vor den String setzen, um die implizite Typkonvertierung durchzuführen. Eine andere Möglichkeit ist die Verwendung von `Number.parseInt()`.

Beispiel:

```javascript
const stringNumber = "42";

const number1 = +stringNumber; // 42
const number2 = Number.parseInt(stringNumber); // 42
```

Um einen String in Großbuchstaben umzuwandeln, kann man die Methode `.toUpperCase()` verwenden.

Beispiel:

```javascript
const text = "hello world";

const upperCaseText = text.toUpperCase(); // "HELLO WORLD"
```

Strings sind in JavaScript unveränderlich (immutable). Das bedeutet, dass Methoden, die einen String modifizieren, tatsächlich einen neuen String zurückgeben, anstatt den ursprünglichen String zu ändern.
