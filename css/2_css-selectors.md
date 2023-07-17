# CSS Selektoren

Ausführung von CSS-Code basierend auf Spezifität:

- Wenn es Konflikte im CSS-Code gibt, wird der Code mit der höchsten Spezifität ausgeführt.

CSS-Selektoren:

- Universal Selector: `*`
- Type Selector: z.B. `body`, `h1`, `button`
- Class Selector: `.classname`
- ID Selector: `#id`
  - IDs sollten nicht verwendet werden, um das Styling zu gestalten, um den CSS-Code generisch zu halten. IDs haben eine höhere Spezifität.
- Attribute Selector: `[attribute]`, z.B. `[type]`, `[type="button"]`, `button[type="button"]`
  - Spezifische Attributwerte können verwendet werden, um gezielt Elemente auszuwählen, z.B. `a[href^="https"]` (Link beginnt mit "https"), `a[href$=".de"]` (Link endet mit ".de"), `a[href*="cake"]` (Link enthält "cake").

Einheiten im CSS:

- `rem` steht für "root em" und bezieht sich auf die Schriftgröße des Root-Elements.
- `em` bezeichnet die Schriftgröße des aktuellen Elements.

BEM Naming Schema:

- BEM steht für "Block Element Modifier" und ist eine Methode zur Benennung von CSS-Klassen, um eine klare und einheitliche Struktur im Styling zu gewährleisten.

Verwendung von `role="list"`:

- Bei Listen sollte man `role="list"` verwenden, wenn man die Bullet Points entfernt, damit der Screen Reader weiß, dass es sich um eine Liste handelt.

Pseudo-Klassen und Pseudo-Elemente:

- Pseudo-Klassen werden mit `:` angegeben, z.B. `:hover`, `:focus`.
- Pseudo-Elemente werden mit `::` angegeben, z.B. `::first-letter`, `::before`, `::after`.
- Pseudo-Elemente sollten nur zum Styling und nicht zur Generierung von Inhalten verwendet werden, da Screenreader diese möglicherweise nicht erkennen.

Kombinatoren:

- Descendant Combinator (Verschachtelung): `SPACE`, z.B. `.main-section .text { }`
- Child Combinator (Direktes Kind): `>`, z.B. `.main-section > article { }`
  - Hier wird das Element `article` nur ausgewählt, wenn es ein direktes Kind von `.main-section` ist.
