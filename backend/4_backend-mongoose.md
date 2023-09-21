# Backend Mongoose

- Mongoose -> Wie ein Datenbanktreiber. Hier für MongoDB
- Mit Mongoose können wir die Daten fest strukturieren
- Treiber darf nicht im Browser laufen, sondern muss aus Sicherheitsgründen im Backend laufen

```bash
npm install mongoose
```

## Sicherheit - Umgebungsvariablen

Damit andere Leute und auch Github keinen Zugriff auf unsere Datenbank haben, speichern wie diese als Umgebungsvariablen
`.env.local`

Zusätzlich **muss** diese Datei in der .gitignore sein

Inhalt:

```js
MONGODB_URI=.../jokes-database?....
```

Nach dem Slash, kommt die Datenbank auf die wir zugreifen wollen

## Praxis

-> Neuer Ordner: db
-> Darin neue Datei: dbConnect.js

Um die Datenbank mit Next.js zu verbinden, gibt es ein Beispiel im Next.js Repo.
Die Verbindung ist sehr kompliziert, und muss jetzt nicht verstanden werden

```js
import mongoose from "mongoose";

const MONGODB_URI = process.env.MONGODB_URI;

if (!MONGODB_URI) {
  throw new Error(
    "Please define the MONGODB_URI environment variable inside .env.local"
  );
}

/**
 * Global is used here to maintain a cached connection across hot reloads
 * in development. This prevents connections growing exponentially
 * during API Route usage.
 */
let cached = global.mongoose;

if (!cached) {
  cached = global.mongoose = { conn: null, promise: null };
}

async function dbConnect() {
  if (cached.conn) {
    return cached.conn;
  }

  if (!cached.promise) {
    const opts = {
      bufferCommands: false,
    };

    cached.promise = mongoose.connect(MONGODB_URI, opts).then((mongoose) => {
      return mongoose;
    });
  }

  try {
    cached.conn = await cached.promise;
  } catch (e) {
    cached.promise = null;
    throw e;
  }

  return cached.conn;
}

export default dbConnect;
```

Mit Mongoose können wir jetzt ein Schemata festlegen (wie eine Blaupause):

- Mit diesen Schemata legen wir die Struktur der Daten fest
- neuer Ordner: `models` (in db)

```js
// --- Joke.js --- //
import mongoose from "mongoose";

const { Schema } = mongoose;

const jokeSchema = new Schema({
  joke: { type: String, required: true },
});

// for mongoose
const Joke = mongoose.models.Joke || mongoose.model("Joke", jokeSchema);
// Schau ob es diese Datenstruktur schon gibt / compiled hat ODER erstelle sie
export default Joke;
```

Mehr Setup braucht man in diesem Fall bei mongoose nicht.
Modelle werden per Konvention auch immer groß geschrieben.

## Queuing the DB (find, findById)

```jsx
import dbConnect from "@/db/dbConnect";
import Joke from "@/db/models/Joke";

export default async function handler(request, response) {
  // connect to database
  await dbConnect();

  if (request.method === "GET") {
    // .find() gibt uns alle Einträge zurück
    const jokes = await Joke.find();
    response.status(200).json(jokes);
  }
}
```

```jsx
import dbConnect from "@/db/dbConnect";
import Joke from "@/db/models/Joke";

export default async function handler(request, response) {
  await dbConnect();
  const { query } = request.query;

  if (request.method === "GET") {
    const joke = await Joke.findById(id);
    if (!joke) {
      return response.status(404).json({ text: "id not found" });
    }
    response.status(200).json(joke);
  }
}
```

Da die IDs jetzt von der Datenbank gegeben werden, muss das auch angepasst werden!
