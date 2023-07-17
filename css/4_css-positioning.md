# CSS Positioning

Positionierung von Elementen in CSS:

- Die Positionierung erfolgt entlang der Z-Achse. Das zuletzt im HTML platzierte Element mit einer Position im CSS liegt immer oben.
- `z-index: $` legt die Ebene fest, auf der sich ein Element befindet. Es funktioniert nicht für Elemente mit `position: static`.

`position: sticky;`:

- Ein Element mit `position: sticky;` scrollt mit, bleibt jedoch an einer bestimmten Position "kleben" (`sticked`) und bewegt sich nicht über diese hinaus.
- Man muss den Abstand (z.B. `top: 0;`) angeben, ab wann das Element "kleben" soll.

`position: fixed;`:

- Ein Element mit `position: fixed;` ist fixiert und bleibt an einer bestimmten Position unabhängig vom Scrollen.
- Man muss immer angeben, wo das Element fixiert werden soll, z.B. `top: 0;`. Es können auch Werte wie `bottom`, `left`, `right` oder eine Kombination davon verwendet werden.
- Negative Werte sind ebenfalls möglich.

Kombination von `position: absolute;` und `position: relative;`:

- `position: relative;` macht das Parent-Element zum neuen Orientierungspunkt für das absolute positionierte Element.
- `position: absolute;` sucht bei seinen Vorfahren nach einem Element mit `position: relative;`. Wenn es keines findet, wird der `body` als Orientierungspunkt verwendet.

Unterschied zwischen `position: fixed;` und `position: sticky;`:

- `position: sticky;` scrollt mit und bleibt an einer bestimmten Position "kleben", bevor es mitgerollt wird (abhängig vom definierten Abstand).
- `position: fixed;` ist fixiert und bleibt unabhängig vom Scrollen an seiner Position.

Weitere erwähnte Konzepte:

- `calc()`: Erlaubt das Ausführen von Berechnungen in CSS.
- Relative Werte: Kurzer Hinweis auf die Verwendung von relativen Einheiten wie `%` oder `em`.
