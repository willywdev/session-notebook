# JavaScript Arrays und Objects

## Arrays

- Liste von Werten in einer Variable gespeichert
- Können auch Objekte und weitere Arrays enthalten
- Jeder Wert hat einen Index, der bei 0 beginnt
- Arrays & Objects werden nur referenziert, nicht direkt im Speicher abgelegt

Array-Syntax: `[ "string", 23, true, "string2" ]`

- Eintrag auslesen: `array[1]` -> Ausgabe: 23
- Array-Größe: `array.length`
- Eintrag aus einem komplexeren Array: `array[2][1]`
- Empfohlen, nur einen Datentyp im Array zu speichern

### Einen Array manipulieren

- Neuen Wert zuweisen: `array[0] = "banana";`
- Neuen Wert am Ende hinzufügen: `array.push("cucumber")`
- Letzten Eintrag entfernen: `array.pop()`

## Objects

- Nicht-primitiver Datentyp
- Bestehen aus Schlüssel-Wert-Paaren
- Kein Index wie bei Arrays
- Objekte können auch andere Objekte beinhalten
- Dot-Notation: `myObject.key` für das Auslesen
- Bracket-Notation: `myObject["age"]`, aber besser vermeiden
- Objekte können Funktionen und mehr beinhalten
- Manipulation von Werten: Überschreiben, Hinzufügen, Entfernen

### Kombination von Arrays & Objekten

- Arrays können Objekte beinhalten
- Objekte können mehrere Arrays beinhalten
- Zugriff auf verschachtelte Werte: `peopleArray[0].name`
