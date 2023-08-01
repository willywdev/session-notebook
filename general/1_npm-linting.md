# NPM und Linting

## Linter

- Ein Linter ist ein Werkzeug, das verwendet wird, um potenzielle Fehler und Codierungsprobleme in Code zu finden.
- Es gibt verschiedene Linter für verschiedene Programmiersprachen, z. B. HTMLHint für HTML und ESLint für JavaScript.

## NPM (Node Package Manager)

- NPM ist der Node Package Manager, der als "App Store" für fremden Code fungiert.
- Es ermöglicht Entwicklern, externe Pakete und Bibliotheken in ihren Projekten zu verwenden.
- Die Installation eines Pakets erfolgt über das Terminal mit `npm install *` oder `npm i`.

## package.json

- Die `package.json` ist eine Datei in einem JavaScript-Projekt, die die Liste der verwendeten NPM-Pakete enthält.
- Sie enthält auch andere Informationen zum Projekt, wie z. B. Name, Version, Beschreibung und Autor.
- Die Datei wird in JSON-Format geschrieben, wobei die Schlüssel in Anführungszeichen stehen.

## node_modules

- Der `node_modules` Ordner ist der Ort, an dem alle NPM-Pakete installiert werden.
- Hier werden die externen Abhängigkeiten des Projekts gespeichert.

## Dev-Dependency und Dependency

- Dev-Dependencies sind Pakete, die nur während der Entwicklung benötigt werden, z. B. zum Testen oder zur Codeformatierung.
- Dependencies sind Pakete, die zur Laufzeit des Codes benötigt werden und tatsächlich in der Produktionsumgebung ausgeführt werden.

## Semantische Versionierung

- Semantische Versionierung ist ein Nummernschema, das verwendet wird, um die Kompatibilität und das Ausmaß der Änderungen in einem Paket oder einer Bibliothek anzugeben.
- Es besteht aus drei Zahlen: Major-Version, Minor-Version und Patch-Version.
- Eine neue Version wird vergeben, wenn es Breaking Changes (Major), neue Funktionen (Minor) oder kleine Änderungen/Bugfixes (Patch) gibt.

## ^ in package.json

- Das `^` vor einer Versionsnummer in der `package.json` bedeutet, dass nur Minor- und Patch-Versionen automatisch aktualisiert werden dürfen.
- Wenn also `^1.2.3` verwendet wird, wird nur die Version `1.2.4` oder `1.3.0` automatisch aktualisiert, aber nicht die Version `2.0.0`.

## scripts in package.json

- Die `scripts` in der `package.json` ermöglichen das Definieren von benutzerdefinierten Befehlen und die Ausführung von Terminalbefehlen.
- Beispiele für Befehle können das Formatieren von Code mit Prettier oder das Ausführen von Testfällen sein.
