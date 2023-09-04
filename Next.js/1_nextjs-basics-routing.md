# Next.js Basics & Routing

- Besonders bei Next.js: Routing
- Bei React war immer nur One-Page-Application
- Routing: Wechseln von mehreren Seiten
- Next.js: Framework für React

## Framework & Library

- Next.js: Framework (baut auf react auf)
  - Gibt ein Gerüst vor
  - Vorgefertigte Lösungen, an die man sich hält
  - Macht vieles einfacher
- React: Library
  - Sammlung von Funktionen und Verfahren

## Next.js

- Wir verwenden den Pages Router verwenden. Es gibt auch den App Router

Was mir machen werden:

- Zero Config Feature
- Routing auf File System
- API Endpunkte bauen
- CSS Support
- Built-in Optimizations ( Images, Font, ... )
- Serverside Rendering: Pre-Rendering von Seiten auf dem Server (Schweres Konzept)
  - Manche Libraries funktionieren nicht richtig mit Serverside Rendering

### Erstellen einer Next.js App

```bash
npx create-next-app@latest .
```

- In der \_document.js wird die HTML Seite erstellt
- index.js stellt unsere Root-Seite dar. Da kommen auch alle Sachen zusammen

## Routing

- Mehrere Seiten erstellen und zwischen diesen navigieren
- Routing basiert auf dem Dateisystem
  - Jede Datei im pages Ordner liegt wird automatisch eine Seite
  - Muss auch ein `export default` haben
- Die URLs sind dann ohne Dateiendungen z.b.: `/about` , `/contact` (außer index.js)
- Ordner können auch index.js haben
- Kein CamelCase, sondern Bindestrich. Weil alles später in den URLs zu sehen ist
- Keine Großbuchstaben als Dateinamen

Nur mit `<a href...` wird die Seite vollständig neugeladen. Next.js hat aber eine besondere Link Komponente:

## Link Komponente

- Content wird vorher schon geladen und der Switch der Seite geht schneller
- VERY IMPORTANT für UX und Speed

```jsx
import Link from "next/link.js";

<Link href=""></Link>;
```

## Image Komponente

- Optimiert Bilder
- Lazy Loading
- Skaliert Bilder automatisch auf eine passende Größe
- ! Breite und Höhe muss immer festgelegt werden

```jsx
import Image from "next/image.js";

<Image src="" alt="" width={} height={} />
```

- Bilder von fremden Domains müssen erst erlaubt werden, in der `next.config.js`:

```js
images: {
	domains: ["URL"], ...
}
```
