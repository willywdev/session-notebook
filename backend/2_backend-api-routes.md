# Backend API Routes

- Eigene API schreiben mit API Routen in Next.js
- Basiert auf dem Dateisystem und Ordnerstruktur
- Serverless functions laufen auf den API Routen
  - JavaScript Funktionen die keinen laufenden State haben
- Serverless functions funktionieren auch besonders gut auf Vercel

## Praxis

- Im pages Ordner -> api Ordner
- Jede Datei im api Ordner ist ein API Endpunkt
- Jede Route hat eine export default function
- Console Logs werden im Terminal angezeigt

```js
// --- /pages/api/jokes/index.js --- //

import { jokes } from "@/lib/data";

export default function handler(request, response) {
  response.status(200).json(jokes);
}
```

```js
// --- /pages/api/jokes/[id].js --- //

import { jokes } from "@/lib/data";

export default function handler(request, response) {
  const { id } = request.query;
  const findJoke = jokes.find((joke) => joke.id === id);

  if (!joke) {
    return response.status(404).json({ status: "Not found" });
  }
  response.status(200).json(findJoke);
}
```
