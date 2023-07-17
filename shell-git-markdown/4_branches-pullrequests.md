# Branches und Pullrequests

Erstellen und Wechseln von Branches:

- `git switch -c your-desired-branch-name`: Erstellt einen neuen Branch mit dem angegebenen Namen und wechselt zu diesem Branch.
- Warum Branches? Nicht alle Entwickler können gleichzeitig auf dem `main`-Branch arbeiten. `main` wird oft als Produktions-Branch verwendet. Für jedes Feature oder jede Änderung wird ein neuer Branch erstellt, um den `main`-Branch zu schützen.
- Man kann auch von einem Branch einen neuen Branch erstellen. Ein Branch ist eine exakte Kopie von `main`.
- Wird `main` referenziert oder ist es nur eine Kopie zu dem Zeitpunkt?
- Neue Branches müssen committet werden, sonst werden die Änderungen im ursprünglichen Branch gemacht.
- Um einen neuen Branch zu veröffentlichen: `git push -u origin [your branch]`.

Pull Request:

- Ein Pull Request wird erstellt, um Änderungen aus einem anderen Branch in den `main`-Branch zu übernehmen.
- Bevor der Pull Request gemerged wird, findet normalerweise ein Code Review statt.

Aktualisieren des lokalen Repositories:

- `git pull`: Aktualisiert das lokale Repository mit allen Änderungen, die remote gemacht wurden.
