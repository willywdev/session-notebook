# CSS Basics

Cascading Style Sheets (CSS):

- Wenn HTML die Struktur der Seite darstellt, ist CSS für das Styling verantwortlich (z.B. Farben, Schriftarten, Größen).
- Cascading: Der Algorithmus im Browser verwendet den CSS-Code von oben nach unten. Das bedeutet, dass Styles auch später überschrieben werden können, aber es ist besser, den Code sauber zu halten.

CSS-Selektoren und Deklarationen:

- Ein CSS-Selektor wählt das Element aus, das gestylt werden soll.
- Die Deklaration enthält die Eigenschaft und den Wert, die dem ausgewählten Element zugewiesen werden sollen.

Einbinden von Stylesheets:

- Um ein Stylesheet hinzuzufügen, verwendet man `<link rel="stylesheet" href="css/styles.css">` im Head-Bereich der HTML-Datei.
- `rel` steht für "Relationship", also welchen Bezug diese Datei zum Dokument hat.

Klassen und IDs:

- Elementen können Klassen (`class=""`) oder IDs (`id=""`) hinzugefügt werden.
- Elemente können mehrere Klassen haben, aber IDs können nur einmal vergeben werden.
- Klassen werden in CSS mit einem Punkt (`.`) und IDs mit einem Hashtag (`#`) angeführt.

Box-Modell:

- Die Berechnung aller Boxen im CSS erfolgt standardmäßig im `content-box`-Modell, d.h. Content + Padding + Border. Das kann umständlich sein, wenn man mit genauen Größen arbeitet.
- Man kann stattdessen das `border-box`-Modell verwenden: `box-sizing: border-box;`. Dadurch wird die Größe auf Content + Padding + Border festgelegt.

Block- und Inline-Elemente:

- Block-Elemente nehmen sich den gesamten verfügbaren Platz innerhalb des Eltern-Elements und erzeugen einen neuen Absatz, eine neue Zeile oder einen neuen Abschnitt.
- Inline-Elemente fügen sich einfach in den Content ein und nehmen nur den Platz ein, den sie benötigen, ohne einen Zeilenumbruch zu erzwingen.
