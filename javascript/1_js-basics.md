# JavaScript Basics I

JavaScript ist verantwortlich für die Funktionalität der Website und die Interaktion mit dem Benutzer. Es ist die einzige Programmiersprache des "Trio" (HTML, CSS, JavaScript) und daher sehr mächtig.

JavaScript einbinden:

- JS kann im HTML-Dokument mit dem `<script>`-Tag eingebunden werden. Es ist empfehlenswert, das `defer`-Attribut hinzuzufügen, um sicherzustellen, dass das Skript erst nach dem Laden des HTML-Dokuments ausgeführt wird.

Custom Attribute (z.B. `data-js`):

- Man kann eigene Attribute hinzufügen, z.B. `data-js="main"`, um Elemente im JS leichter auswählen zu können.

JavaScript Basics:

- `console.log("Hello World");`: Eine einfache Ausgabe in der Konsole.
- Datentypen: String, Numbers, Booleans.
- Variablen: `const` und `let`.
- Document Object Model (DOM) und `querySelector` für die Auswahl von Elementen im HTML.

Variablen Scope:

- Variablen haben in JavaScript einen bestimmten Gültigkeitsbereich, der durch ihre Position in der Code-Struktur festgelegt wird.

Seperations of Concerns:

- Die Trennung von Namen in HTML, CSS und JS verhindert mögliche Konflikte und sorgt für eine klare Struktur im Code.

JavaScript und Klassen/IDs:

- Die Verwendung von Klassen und IDs im JS sollte vermieden werden, um die Trennung der Zuständigkeiten (Seperations of Concerns) zu wahren.

`console.clear();`: Löscht die Konsole.

Nicht-primitiver Datentyp "Objekt":

- Objekte sind komplexe Datentypen, die mehrere Eigenschaften und Werte enthalten können.

Nicht-primitiver Datentyp "Array":

- Arrays sind geordnete Listen von Werten, die in eckigen Klammern stehen und durch Kommas getrennt sind.

Events:

- Einführung in das Thema "Events", z.B. `addEventListener`.

CSS Modifier:

- Wenn man spezifische Elemente innerhalb einer Klasse bearbeiten möchte, kann man sogenannte "Modifier" verwenden, z.B. `button--light` und `button--dark`.
