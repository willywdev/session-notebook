# JavaScript Unit Testing

- Tests für den eigenen Code = Sicherstellen, dass robuster und guter Code
- Bugs minimieren und frühzeitig entdecken
- Minimiert Fehlersuche
- Dokumentationshilfe
- Static Testing = Linter (Rechtschreibprüfung, Syntax Errors, ...)
- Integration Test = Wie funktionieren die Einheiten miteinander und zueinander?
- End to End Test = Helper Robot, that behaves like a user to click around and verify that it functions correctly
- "Test Driven" Development = Erst die Tests und dann die Funktionen

## Unit Tests

- Testen eine in sich geschlossene Einheit (z.b. eine Funktion)
- Kleinste Art von Tests
- NPM Library für Tests:

  [Jest](jestjs.io)

  `npm i -D jest`

- Desto größer die Funktion, desto mehr müssen wir testen
- Externe Abhängigkeiten erschweren Tests
- Wichtig: Funktion muss etwas returnen
- Funktion braucht export

## ToDo

1. Neue Datei anlegen `greet.test.js`
   - Gleichen Namen wie die zu testende Datei
2. Die zu testende Einheit importieren
3. Jest nutzen & Test schreiben:
   - `test( "HILFSTEXT", () => {} )`
   - `expect(result).toBe("")` (Methode nennt man Matcher)
4. `npm run test`

```javascript
test("return 'Hello Jane!' if called with greet('Jane')", () => {
  const result = greet("Jane");
  expect(result).toBe("Hello Jane!");
});
```

```javascript
test("returns 'Hello Stranger!' if called greet()", () => {
  const result = greet();
  expect(result).toBe("Hello Stranger!");
});
```

```javascript
test("returns 'Hello Coach!' if called greet('Niklas')", () => {
  const result = greet("Niklas");
  expect(result).toBe("Hello Coach!");
});
```
