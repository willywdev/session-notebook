# CSS Struktur und Specificity

Bei der Menge an CSS, die man schreibt, kann man leicht den Überblick verlieren. Daher ist es wichtig, eine Struktur festzulegen, um die Lesbarkeit und Wartbarkeit des Codes zu gewährleisten.

Cascading in CSS:

- Wenn zwei Selektoren miteinander konkurrieren, gewinnt der spezifischere Selektor (Specificity).
- Die Specificity wird durch die Kombination von Selektoren bestimmt, z.B. durch IDs, Klassen oder Elementnamen.
- Reihenfolge: Wenn die Specificity gleich ist, entscheidet die Reihenfolge im Code darüber, welcher Stil angewendet wird.
- Vererbung: Bestimmte Eigenschaften werden auf Kind-Elemente vererbt, z.B. `font-family` oder `color`.

Specificity:

- Je spezifischer der Selektor, desto höher ist die Priorität in der Kaskade.
- Inline Styles und `!important` haben die höchste Specificity.
- Der Universal-Selektor (`*, *::before, *::after`) hat die geringste Specificity.
- Die Specificity kann in komplexen Fällen schwierig zu berechnen sein, aber es gibt Tools wie das Specificity Calculator, um zu helfen.

Order (Reihenfolge):

- Wenn die Specificity gleich ist, wird der Stil angewendet, der später im Dokument kommt.

Inheritance (Vererbung):

- Bestimmte Eigenschaften werden von Eltern-Elementen auf Kind-Elemente vererbt, z.B. `font-family` oder `color`.

CSS-Klassennamen und BEM (Block Element Modifier):

- Eine Methode zum Benennen von Klassen ist BEM (Block Element Modifier).
- BEM besteht aus drei Teilen: Block, Element und Modifier. Damit kann man Klassen besser strukturieren und benennen.

Mehrere CSS-Dateien und @import:

- Es ist hilfreich, den CSS-Code in mehrere Dateien aufzuteilen, um die Struktur zu verbessern und den Code besser zu organisieren.
- Man kann die `@import`-Anweisung verwenden, um andere CSS-Dateien einzubinden.

Variablen / Custom Properties:

- Mit `:root {}` kann man globale Variablen oder Custom Properties definieren.
- Mit `var(--variable-name)` kann man die Werte der Variablen verwenden. Dadurch wird der Code flexibler und leichter wartbar.
