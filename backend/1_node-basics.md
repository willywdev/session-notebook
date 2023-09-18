# Backend Basics

- HTTP Server aufsetzen mit Node.js
  - [HTTP Cats](https://http.cat/)
- Frontend zu Backend: GET /products , GET /image-1.jpg , GET /api/products/1
- Server wartet die ganze Zeit auf Befehle
- Serveraktivitäten werden z.T. im Network-Tab des Browsers angezeigt

```js
--- server.js ---

import { createServer } from 'node:http';

export const server = createServer((request, response) => {
	response.statusCode = 200;
	// Jeder Response die wir senden, muss auch beendet werden. Z.B. indem 	   wir dem Client etwas übersenden:
	response.end("Hello World!");
});
```

```js
--- index.js ---

import { server } from "./server.js";

const port = 9000;
server.listen(port, () => {
	// Wird zurückgegeben, wenn der Server gestartet wird
	console.log("Server is running on http://localhost:" + port + "/");
});
```

## Requests definieren

```jsx
--- server.js ---

export const server = createServer((request,response) => {
	if (request.url === "/hello") {
		response.statusCode = 200;
		response.end("Hello World!!!");
	} else if (request.url === "/bye") {
		response.statusCode = 200;
		response.end("Goodbye!");
	} else {
		response.statusCode = 404;
		response.end("Not found");
	}
})
```
