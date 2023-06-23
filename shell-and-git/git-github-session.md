Am vierten Tag wurde das Thema "Lokal mit Git arbeiten / Remote zu Github" behandelt. Es wurde erklärt, wie Änderungen an Github übermittelt werden können und wie man Repositories klonen kann.

Ein Git-Repository kann mit dem Befehl "git init" im gewünschten Ordner erstellt werden. Alle Commits werden im unsichtbaren ".git"-Ordner gespeichert. Das Hinzufügen des Begriffs "main" zum Pfad wird am nächsten Tag behandelt.

Das Löschen eines Git-Repositories erfolgt durch den Befehl "rm -rf .git". Das Umbenennen des Ordners stellt kein Problem dar. Die Datei ".gitignore" (ohne Endung) enthält eine Liste von Dateien, die im Projekt enthalten sind, aber von Git nicht verfolgt werden sollen, z.B. Passwörter von Datenbanken oder API-Schlüssel. Auf macOS sollte die Datei ".DS_Store" in die ".gitignore" aufgenommen werden, da sie automatisch erstellt wird und Konfigurationen über den vorhandenen Ordner enthält.

Mit dem Befehl "echo ".DS_Store" > .gitignore" kann der Inhalt der Datei festgelegt werden. "code ." öffnet Visual Studio Code im aktuellen Pfad.

Git erkennt Dateien in verschiedenen Zuständen. "untracked" bedeutet, dass sie von Git nicht verfolgt werden. Mit "git status" kann der aktuelle Status des Repositories abgefragt werden. Mit "git add <file>" können Dateien dem Stage hinzugefügt werden, und mit "git commit -m "message"" werden die Dateien commitet und landen im Zustand "commited". "git log --oneline" zeigt die Git-Historie an.

Wenn Dateien nach dem Commit geändert werden, wechseln sie in den Zustand "modified" und müssen erneut committed werden. Um mehrere Dateien hinzuzufügen, kann "git add ." verwendet werden. Mit "git restore --staged <file>" können Dateien aus dem Stage entfernt und in den Zustand "modified" gebracht werden.

Für die Verbindung mit Github kann mit "git remote -v" überprüft werden, ob bereits ein Remote-Repository verbunden ist. Um ein neues Repository auf Github zu erstellen und damit zu verbinden, werden die angezeigten Code-Optionen verwendet. Mit "git push" werden lokale Änderungen auf das Remote-Repository hochgeladen. "-u" steht für Upstream und wird beim ersten Mal benötigt.

Um ein Repository zu klonen, wird "git clone" gefolgt vom SSH-Code verwendet. Das Repository wird direkt geklont und im Terminal als Repository erkannt.
