# Git und Github

Kommunikation mit GitHub:

- Repositories sind wie spezifische Ordner (Projekte), in denen unsere Quelldateien liegen.
- `commit`: Speichert die von uns vorgenommenen Änderungen.
- Git sammelt die Projekt-Historie.

Git-Repository erstellen:

- `git init`: Erstellt ein neues Git-Repository im aktuellen Ordner.
- Alle Commits werden im unsichtbaren .git-Ordner gespeichert.
- In Pfaden erscheint standardmäßig "main". Die Bedeutung von "main" wird morgen gelernt.
- Löschen eines Git-Repositories: `rm -rf .git` (einfaches Löschen des Ordners).

Umgang mit `.gitignore`:

- `.gitignore` ist eine Datei und kein Ordner (ohne Dateiendung).
- Es enthält eine Liste von Dateien, die im Projekt vorhanden sind, aber nicht von Git verfolgt werden sollen (z.B. Passwörter für Datenbanken oder API-Schlüssel).
- Auf macOS ist `.DS_Store` eine typische Datei, die hinzugefügt wird (manchmal automatisch generiert und enthält Konfigurationen über den vorhandenen Ordner).
- Über das Terminal: `echo ".DS_Store" > .gitignore` fügt `.DS_Store` der `.gitignore`-Datei hinzu.

Git-Status und Zustände von Dateien:

- `git status`: Zeigt den aktuellen Status des Repositories an.
- `untracked`: Dateien, die von Git nicht erkannt werden.
- `?`: Kennzeichnet `untracked` Dateien, gefolgt von der Anzahl der Dateien, die Git nicht erkennt.
- `staged`: Dateien, die zur Staging Area hinzugefügt wurden (Vorstufe vor dem Commit).
- `modified`: Dateien, die nach dem Commit erneut geändert wurden.

Git-Befehle für das Hinzufügen und Commiten:

- `git add <file>`: Fügt eine Datei zur Staging Area hinzu.
- `git commit -m "message"`: Commitet alle gestageten Dateien mit einer Nachricht.
- `git log --oneline`: Zeigt die Git-Historie an.

Mehrere Dateien hinzufügen:

- `git add .`: Fügt den gesamten Ordner zur Staging Area hinzu.

Rückgängigmachen von Staging-Änderungen:

- `git restore --staged <file>`: Entfernt eine Datei aus der Staging Area und fügt sie zu den modifizierten Dateien hinzu (Änderungen bleiben erhalten, aber werden nicht committet).
- Ohne `--staged`: Macht alle Änderungen in der Datei seit der letzten Staging Area rückgängig.

Verbindung mit GitHub:

- `git remote -v`: Überprüft, ob ein Remote-Repo bereits verbunden ist.
- Neues Repo auf GitHub erstellen.
- `git remote add origin <GitHub-URL>`: Verbindet das lokale Repo mit dem Remote-Repo auf GitHub.
- `git push -u origin main`: Pushed lokale Änderungen auf das Remote-Repo (Upstream-Option `-u` wird beim ersten Mal benötigt).

Repository klonen:

- SSH auswählen.
- `git clone <SSH-Code>`: Klonen eines Repositories (wird als Repo im Terminal erkannt).
