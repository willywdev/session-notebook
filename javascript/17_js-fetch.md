# JavaScript Fetch

## API

- API = Application Programming Interface
- Stellt Daten zur Verfügung eines externen Dienstes / App / Website
- Muss angerufen werden. Meist mit einem API - Key, es gibt allerdings auch frei zugängliche
- Mit async Functions warten wir, bis die Daten von der API zurückgekommen sind.
- Ist mit Funktionen und Regeln bestückt, wie wir die API zu handeln haben
- Der Entwickler der API hat entschieden, wie man die API nutzt. Meist gibt es Dokumentationen dazu

## WebAPI

- Besondere APIs die vom Browser zugegriffen werden können
- Solange ein Programm / App im Browser läuft, sind WebAPIs verfügbar
- [MDN Web APIs](https://developer.mozilla.org/en-US/docs/Web/API?retiredLocale=de)

## `fetch()`

- Kommt oft als json zurück

```javascript
async function getJoke() {
  jokeSection.innerHTML = "";
  try {
    const response = await fetch("https://....com/api/");
    console.log(response);
  } catch (error) {
    console.log(error);
  }
}
```

- Status aus der Response ist relevant:
  - 200 - 299: Alles okay (okay:true)
  - 400 - 499: Fehlgeschlagen (okay:false)
  - 500 - 599: Server Error (okay:false)

```javascript
async function getJoke() {
  jokeSection.innerHTML = "";
  try {
    const response = await fetch("https://....com/api/");
    console.log(response);
    // Status handling
    if (!response.ok) {
      console.error("Bad Response");
    } else {
      const jokeData = await response.json();
      console.log(jokeData.joke);
    }
  } catch (error) {
    console.log(error);
  }
}
```
