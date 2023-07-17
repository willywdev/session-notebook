# JavaScript Conditions & Booleans

**Was sind Conditions?**
Conditions in JavaScript sind Ausdrücke, die entweder true (wahr) oder false (falsch) auswerten. Sie werden in Kontrollstrukturen wie `if`-Anweisungen verwendet, um Code basierend auf bestimmten Bedingungen auszuführen oder zu überspringen.

**Booleans**
In JavaScript gibt es den Datentyp "Boolean", der nur zwei Werte haben kann: true oder false. Boolesche Werte werden oft in Conditions verwendet, um Entscheidungen zu treffen.

**Truthy / Falsy**
Neben den expliziten true und false Werten haben JavaScript-Ausdrücke auch truthy oder falsy Werte. Truthy-Werte sind Werte, die als wahr betrachtet werden, wenn sie in einer Bedingung verwendet werden, während falsy-Werte als falsch betrachtet werden. Beispiele für falsy-Werte sind 0, "", undefined und null. Alles andere gilt als truthy.

**Vergleichsoperatoren**
JavaScript verfügt über verschiedene Vergleichsoperatoren, mit denen Werte verglichen werden können:

- `>` : größer als
- `<` : kleiner als
- `==` : gleich
- `===` : strikt gleich (vergleicht auch den Datentyp)
- `!=` : ungleich
- `!==` : strikt ungleich
- `<=` : kleiner oder gleich
- `>=` : größer oder gleich

**Logische Operatoren**
Logische Operatoren werden verwendet, um mehrere Bedingungen zu kombinieren:

- `&&` : logisches UND, liefert true, wenn beide Bedingungen true sind
- `||` : logisches ODER, liefert true, wenn mindestens eine Bedingung true ist

**Ternary Operator**
Der Ternary Operator ist eine verkürzte Schreibweise für eine if-else-Anweisung. Er ermöglicht es, eine Bedingung in einer einzigen Zeile zu überprüfen und einen Wert basierend auf der Bedingung zurückzugeben.
Beispiel: `const age = 18;` `const isAdult = age >= 18 ? true : false;`

**Type Coercion (Typ-Nötigung)**
JavaScript versucht oft, verschiedene Datentypen in Bedingungen zu vergleichen oder zu kombinieren. Wenn dies der Fall ist, wird eine implizite Typumwandlung durchgeführt, um die Werte vergleichbar zu machen. Dies wird als Typ-Nötigung bezeichnet.
Beispiel: `if (4) { console.log("true"); }` Hier wird die Zahl 4 zu einem truthy Wert zwangsweise umgewandelt und die Ausgabe ist "true".
