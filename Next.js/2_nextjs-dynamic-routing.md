# Next.js Dynamic Routing

Bisher hatten wir statische Routes. Das ganze geht auch dynamisch.
Beispiel: 300 verschiedene Bücher mit eigenem Pfad.
Dynamisch heißt in diesem Fall keine Dateien zu hardcoden, sondern dynamisch erstellen zu lassen.

```js
[slug].jsx;

// Durch die eckigen Klammern, kann man Next.js sagen, dass hier dynamisch Routen erstellt werden
```

-> Dies würde aber dafür sorgen, dass man alles im Pfad eingeben kann. z.B. "movies/laksjddls/" und es würde keinen Fehler erzeugen

## useRouter - Hook von Next.js für Dynamic Routes

```jsx
import { useRouter } from "next/router";

const router = useRouter();

router.query;
// returns an object with the key we named the dynamic route file (e.g. slug) and the value of the URL (e.g. the-avengers)

const { slug } = router.query;
```

-> Riesiges Objekt mit Methoden

## ToDo

1. Ordner / File dynamisch machen mit `[...].js`
2. useRouter verwenden

## Links dynamisch machen

```jsx
<Link href={`/movies/${movie.slug}`}>{movie.title}</Link>
```

- Für Template Strings in JSX brauchen wir `{ }`
- Um in Template Strings Variablen zu verwenden brauchen wir `${ }`

## Head Komponente aus Next.js

```jsx
import Head from "next/head";

<Head>
  <title>{title}</title>
</Head>;
```

-> Mit der Head Komponente kann man den HTML Titel ändern (<title></title>)
