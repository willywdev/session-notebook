# Advanced git

## Merge-Konflikte

- Nicht vermeidbar
- Passieren, wenn viele Entwickler an einem Projekt arbeiten. Das war bisher nicht der Fall, wird aber in der Zukunft definitiv der Fall sein
- Pull Request = Quality Gate (Qualitätskontrolle)
- Merge Konflikt = Widerspruch in den Daten (z.B. zwei parallele Branches die an der gleichen Datei arbeiten)

## Beispiel: Main verändert, nach Pull Request auf Branch

```bash
git pull
git switch greet-coach
git merge main
// go to VSCODE to fix Merge conflict
git add .
git commit -m "resolve merge conflict"
git push
```

- Man muss in den neuen Branch switchen, der den Merge Konflikt verursacht hat. Grundsätzlich arbeitet man nicht auf main!
- "Man sollte sich erst um Probleme kümmern, wenn sie entstanden sind."
