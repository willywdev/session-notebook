# JavaScript Structure

Um mehr Übersicht und Struktur im Code zu schaffen, können JavaScript-Dateien aufgeteilt werden, um in sich geschlossene Codeblöcke zu trennen.

## Seperation of Concerns

- Seperation of Concerns (Trennung von Anliegen) ist ein Prinzip, bei dem der Code in klar definierte Teile aufgeteilt wird, sodass jede Einheit eine spezifische Aufgabe erfüllt und sich nicht mit anderen Belangen überschneidet.
- Dies verbessert die Wartbarkeit und Lesbarkeit des Codes.

## Utilities in utils.js

- Allgemeine Funktionen, Variablen und Objekte werden in der Datei utils.js gespeichert.
- Es ist eine gängige Konvention, solche Hilfsfunktionen in einer utils-Datei zu speichern.

## Import und Export

- Um Code zwischen verschiedenen JavaScript-Dateien zu teilen, können Module verwendet werden.
- Mit `import` und `export` können Module in andere Dateien importiert und exportiert werden.
- In der Haupt-JavaScript-Datei wird `import {variableName} from "./utils/author.js";` verwendet, um die benötigten Funktionen oder Variablen aus einer anderen Datei zu importieren.
- In der zu exportierenden Datei wird `export` vor der Variable oder Funktion verwendet.

## Verwendung von Modulen

- In der HTML-Datei muss `type="module"` im `<script>`-Tag angegeben werden, um JavaScript-Module zu verwenden.

## Komponenten in React

- Komponenten werden in React in Funktionen gespeichert, die die Komponente `returnen`.
- Diese Funktionen werden per Konvention großgeschrieben, um sie von normalen Funktionen zu unterscheiden.

## Default Export

- Ein Modul kann einen sogenannten Default Export haben, bei dem der Name des Exports beim Importieren nicht in geschweiften Klammern angegeben werden muss.
- Das wird in React oft verwendet, und es darf pro Datei nur einen Default Export geben.
- Die Syntax für den Default Export lautet `export default function Header()`.
- Beim Importieren wird dann `import Header from "./";` verwendet.
