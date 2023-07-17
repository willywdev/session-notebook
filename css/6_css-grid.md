# CSS Grid

CSS Grid, zu Deutsch "Raster", ist ein leistungsstarkes Layout-System in CSS. Es eignet sich besonders gut für asymmetrische Designs und komplexe Layouts. Man kann sich CSS Grid wie eine Tabelle mit Reihen und Spalten vorstellen.

Die wichtigste Eigenschaft, um ein CSS Grid zu erstellen, ist `display: grid;`. Damit werden alle _direkten_ Kinder des Containers zu Grid-Items.

Mit `grid-template-columns: 200px;` kann man eine Spalte mit einer Breite von 200 Pixeln erstellen. Für mehrere Spalten kann man z.B. `grid-template-columns: 200px 200px 200px;` verwenden, um drei Spalten zu erstellen.

Eine besondere Einheit bei Grid ist `fr` (Fraction). `1fr` bedeutet, dass das Grid-Item so viel Platz einnehmen soll, wie möglich. Wenn man mehrere `1fr` verwendet, teilen sie sich den verfügbaren Platz gleichmäßig auf.

Man kann auch die `repeat()`-Funktion nutzen, um wiederkehrende Spalten oder Reihen zu erstellen, z.B. `grid-template-columns: repeat(4, 1fr);`.

Grid-Items können auch direkt mit `grid-column` und `grid-row` positioniert werden, z.B. `grid-column: span 2;` für 2 Spalten breit oder `grid-row: 1 / span 2;` für 2 Reihen hoch.

Eine praktische Abkürzung für komplexe Layouts bietet `grid-template-areas`, bei dem man ein Template mit benannten Bereichen erstellt und den Grid-Items dann diese Bereiche zuweisen kann.

Zusammenfassend:

- `display: grid;`: Erstellt ein CSS Grid.
- `grid-template-columns`: Legt die Spaltenbreiten fest.
- `grid-column`: Positioniert das Grid-Item in den Spalten.
- `grid-row`: Positioniert das Grid-Item in den Reihen.
- `grid-template-areas`: Erstellt ein Template mit benannten Bereichen.
- `grid-area`: Weist den Grid-Items die benannten Bereiche zu.
- `grid-auto-columns`: Legt die Größe für automatisch erzeugte Spalten fest.
- `grid-auto-rows`: Legt die Größe für automatisch erzeugte Reihen fest.
