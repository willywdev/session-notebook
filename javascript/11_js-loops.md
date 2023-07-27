# JavaScript Loops

## While Loop

```javascript
let counter = 0;
while (counter < 20) {
  // Code ausführen
  counter++;
}
```

- Solange die Bedingung `true` ist, wird der Codeblock ausgeführt.
- Achtung: Wenn keine endliche Bedingung angegeben wird, kann dies zu einer Endlosschleife führen und die Webseite abstürzen.

## For Loop

```javascript
for (let i = 0; i < 10; i++) {
  // Code ausführen
}
```

- Ähnlich wie der While Loop, erfordert jedoch die Angabe einer Variable (Iteration Counter), einer Bedingung und einer Manipulation der Variable (Afterthought).
- Wird nicht mehr so häufig verwendet, da viele Anwendungsfälle durch bestehende JavaScript-Methoden ersetzt werden können.

## For In Loop

- Wird nur für Objekte verwendet:

```javascript
const user = { name: "alex", age: 20 };
for (const key in user) {
  // Code ausführen
  console.log(user[key]);
}
```

- Es wird eine neue Variable erstellt, die ähnlich wie ein Iteration Counter ist, um auf die Schlüssel-Werte-Paare des Objekts zuzugreifen.

## For Of Loop

- Wird nur für Arrays verwendet:

```javascript
const fruits = ["apple", "peach", "banana"];
for (const fruit of fruits) {
  // Code ausführen
  console.log(fruit);
}
```

- Der For Of Loop ermöglicht es, direkt auf die Werte eines Arrays zuzugreifen, anstatt auf die Indizes.
