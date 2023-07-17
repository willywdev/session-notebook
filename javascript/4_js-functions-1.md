# JavaScript Funktionen I

## Definieren einer Funktion (Function Declaration)

Eine Funktion in JavaScript wird mit dem `function`-Schlüsselwort und einem Namen definiert, gefolgt von runden Klammern und einem Funktionskörper in geschweiften Klammern. Der Funktionskörper enthält den Code, den die Funktion ausführt, wenn sie aufgerufen wird.

Beispiel:

```javascript
function greet() {
  console.log("Hello!");
}
```

## Funktion aufrufen (Function Call)

Eine Funktion wird aufgerufen, indem ihr Name gefolgt von runden Klammern geschrieben wird.

Beispiel:

```javascript
greet(); // Ruft die Funktion greet auf und gibt "Hello!" in der Konsole aus.
```

## Parameter

Funktionen können Parameter entgegennehmen, die als Platzhalter für Werte dienen, die beim Funktionsaufruf übergeben werden. Parameter werden in den runden Klammern bei der Definition der Funktion angegeben.

Beispiel:

```javascript
function printSum(a, b) {
  console.log(a + b);
}
```

In diesem Beispiel hat die Funktion `printSum` zwei Parameter `a` und `b`, die beim Aufruf der Funktion Werte entgegennehmen. Beim Aufruf der Funktion müssen diese Werte angegeben werden.

## Scope (Gültigkeitsbereich) von Variablen

In JavaScript gibt es den Begriff "Scope", der den Gültigkeitsbereich einer Variablen beschreibt. Variablen, die innerhalb einer Funktion definiert werden, haben nur einen Gültigkeitsbereich innerhalb dieser Funktion, das nennt man "Function Scope". Variablen, die außerhalb von Funktionen definiert werden, haben einen globalen Gültigkeitsbereich und können von überall im Code aus zugegriffen werden.

Beispiel:

```javascript
function greet() {
  const message = "Hello!";
  console.log(message);
}

greet(); // Gibt "Hello!" aus
console.log(message); // Würde einen Fehler auslösen, da "message" nur in der Funktion greet gültig ist.
```

Es ist wichtig, den Scope von Variablen so klein wie möglich zu halten, um Fehler zu vermeiden und den Code besser wartbar zu machen.
