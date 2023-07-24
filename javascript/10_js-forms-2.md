# JavaScript Forms II

## HTML

Zu Formularen gehört auch die Überprüfung der eingegebenen Daten bzw. das Festlegen der Daten, die eingegeben werden dürfen.

Die wichtigsten Attribute für `input`-Felder sind:

- `type="text"`, `type="password"`, `type="email"`, `type="number"`, `type="date"`

Um ein Input-Feld verpflichtend zu machen, kann man das `required` Attribut verwenden:

```html
<input type="text" required />
```

Weitere nützliche Attribute sind:

- `minlength="3"`: Bestimmt die Mindestanzahl der Zeichen eines Input-Felds.
- `maxlength="30"`: Bestimmt die Maximalanzahl der Zeichen.
- `min="5"` und `max="30"`: Für Zahlen-Inputs und andere Inputs, die mit Werten arbeiten.

## JavaScript

_Input Event_
Das Input Event wird jedes Mal ausgelöst, wenn sich der Inhalt eines Input-Felds ändert. Es reagiert also auf jegliche Änderungen:

```javascript
passwordInput.addEventListener("input", () => {
  // Code ausführen
});
```

_Formular Reset_
`form.reset();`
Mit dieser Methode werden alle Eingaben in einem Formular zurückgesetzt.

_Fokussieren des Input-Felds_
`nameInput.focus()`
Mit `focus()` kann das Input-Feld `nameInput` im Formular nach dem Absenden direkt wieder fokussiert werden.
