# CSS Flexbox

Flexbox ist ein Layout-Modell in CSS, das hilft, Elemente in einer flexiblen Weise anzuordnen.

Grundlegendes zur Flexbox:

- Flexbox besteht aus einem Flex-Container und Flex-Items (Kinder des Containers).
- `display: flex;` definiert einen Flex-Container.
- `flex-direction: row;` ist die Standardausrichtung (X-Achse), kann aber mit `flex-direction: column;` geändert werden (Y-Achse).
- `justify-content` wird für die Ausrichtung in der Hauptachse verwendet, abhängig von der `flex-direction`.
- `align-items` wird für die Ausrichtung in der Nebenachse verwendet, abhängig von der `flex-direction`.

Flexbox-Nesting:

- Flexboxen können ineinander verschachtelt werden.
- Die Kinder einer Flexbox sind relevant, also sollte man darauf achten, welchen Parent man zu einem Flex-Container macht, um die richtige Anzeige zu gewährleisten.

Responsive Design mit Flexbox:

- Flexbox kann für Desktop-Layouts verwendet werden, aber für mobile Ansichten sollten zusätzliche Anpassungen vorgenommen werden.
- `flex-wrap` ermöglicht es, dass Flex-Items bei Platzmangel auf die nächste Zeile umgebrochen werden (`flex-wrap: wrap`).
  Wenn man dieses Verhalten nicht möchte, kann man `flex-wrap: nowrap` verwenden.

Lücken in Flexbox-Layouts:

- Mit `gap` kann man Lücken zwischen Flex-Items festlegen. Es funktioniert sowohl in der X- als auch in der Y-Achse.
- `gap` ist jedoch nicht so flexibel wie `justify-content` und kann weniger responsive sein.
