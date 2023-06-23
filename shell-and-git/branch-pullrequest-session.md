# Github Branching

Wenn du an einem Projekt arbeitest, insbesondere im Team, möchtest du an Funktionen unabhängig voneinander arbeiten, sodass sie sich nicht auf die Arbeit anderer auswirken.<br> Git bietet uns Branches, um unsere aktuelle Arbeit von dem gemeinsamen Codebase des Teams fernzuhalten, bis sie abgeschlossen ist.

Die gemeinsame Codebasis des Teams wird normalerweise im "main"-Branch gehalten. Wenn du an einer neuen Funktion arbeitest, kannst du folgendermaßen vorgehen:

1. Erstelle einen neuen Feature-Branch und arbeite an diesem Branch.
2. Commite deine Arbeit auf dem neuen Branch - der Hauptbranch bleibt unverändert.
3. Beende die Arbeit an der neuen Funktion, teste die neue Funktionalität und lass andere Entwickler deine Arbeit überprüfen.
4. Merge deinen Feature-Branch in den Hauptbranch, sodass deine gesamte Arbeit im Hauptbranch enthalten ist.

Namensgebung von Branches:
Es ist ratsam, kurze beschreibende Namen für deine Feature-Branches zu verwenden, z.B. "contact-form". Wir empfehlen, Bindestriche als Trennzeichen zu verwenden, da sie den Namen lesbarer machen.

Git Pull Requests:
GitHub bietet uns Pull Requests (PR), die wir als bequemen Weg verwenden können, um Reviews der Arbeit auf einem Feature-Branch anzufordern. Ein Pull Request ist eine Anfrage, einen Branch in einen anderen Branch zu mergen. Andere Entwickler überprüfen den PR und schlagen Änderungen vor. Wenn ein Pull Request genehmigt wird, können wir den Feature-Branch in den Hauptbranch mergen.

Grundlegender Workflow für einen Pull Request:

1. Erstelle einen neuen Branch mit "git switch -c <Branchname>".
2. Mache Änderungen am Code / schreibe deinen Code für das Feature.
3. Pushe die Änderungen und den neuen Branch mit "git push -u origin <Branchname>" (nachdem du dies einmal getan hast, kannst du "git push" für diesen Branch verwenden).
4. Erstelle auf GitHub einen Pull Request vom neuen Branch in den Hauptbranch.
5. Teile den Pull Request mit deinem Team.
6. Überprüfe den Pull Request, implementiere Änderungen, falls erforderlich, pushe erneut, um den Pull Request zu aktualisieren, bis er genehmigt wird.
7. Mergen den Pull Request in den Hauptbranch.
8. Vergiss nicht, im Hauptbranch auf deinem lokalen Computer "git pull" auszuführen.
9. Lösche den neuen Branch auf GitHub und lokal.
