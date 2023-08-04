# JavaScript Array Methods 2

## .includes

- Die Methode `.includes()` gibt `true` oder `false` zurück und überprüft, ob ein bestimmtes Element in einem Array vorhanden ist.
- Es wird nicht nur der Wert überprüft, sondern auch, ob das Element selbst existiert.

## .find & .findIndex

### .find

- Die Methode `.find()` gibt das **erste Element** zurück, das die angegebene Bedingung erfüllt.
- Wenn kein passendes Element gefunden wird, gibt `.find()` `undefined` zurück.
- Es wird nur das **erste** passende Element zurückgegeben.

### .findIndex()

- Die Methode `.findIndex()` gibt den Index des ersten Elements zurück, das die angegebene Bedingung erfüllt.
- Wenn kein passendes Element gefunden wird, gibt `.findIndex()` `-1` zurück.

## .sort

- Die Methode `.sort()` wird verwendet, um ein Array zu sortieren.
- Für das Sortieren nach Zahlen kann eine Funktion mit den Parametern `a` und `b` angegeben werden.
- Die Funktion vergleicht die Elemente und ändert die Reihenfolge der Elemente im Array entsprechend.
- Wenn das Ergebnis größer als 0 ist, wird `a` nach `b` sortiert.
- Die Methode überschreibt die Sortierung des Original-Arrays.

## .slice

- Die Methode `.slice()` wird verwendet, um eine flache Kopie eines Arrays zu erstellen.
- Dies wird oft verwendet, um ein Array zu kopieren, um das Original-Array nicht zu verändern.

## .some

- Die Methode `.some()` testet, ob mindestens ein Element in einem Array eine bestimmte Bedingung erfüllt.
- `.some()` gibt `true` oder `false` zurück.

## .every

- Die Methode `.every()` testet, ob alle Elemente in einem Array eine bestimmte Bedingung erfüllen.
- `.every()` gibt `true` zurück, wenn alle Elemente die Bedingung erfüllen, andernfalls gibt es `false` zurück.
