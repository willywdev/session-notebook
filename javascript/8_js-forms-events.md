# JavaScript Forms und Events

Standardverhalten von Formularen: Neuladen der Seite + Speichern der Daten in der URL + Daten im Formular werden gelöscht.

## Verhindern des Standardverhaltens

Beim Submit-Event `event.preventDefault()` verwenden, um das Standardverhalten zu unterbinden und die Seite nicht neu zu laden.

## 1. Möglichkeit, Elemente aus einem Formular zu holen

`event.target` ist ein großes Event-Objekt, das auf alle Elemente im Formular zugreifen kann.

- Mit `event.target.elements` erhält man eine HTML Collection der Formularelemente.
- Auf einzelne Elemente zugreifen mit dem "name"-Attribut, z.B.: `event.target.elements.firstName`.
- Um auf den Inhalt zuzugreifen: `event.target.elements.firstName.value`.

## 2. Möglichkeit, Elemente aus einer Form zu holen

`const formData = new FormData(event.target);`

- Erstellt eine Instanz der Klasse FormData und enthält die Einträge des Formulars.

`const data = Object.fromEntries(formData);`

- Wandelt die Einträge des Formulars in ein Objekt um.
