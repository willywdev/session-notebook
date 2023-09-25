# Backend Update & Delete

## Update

- Methode: PUT
- Update erzeugen mit **Überschreiben**
- Es gibt auch die Methode PATCH. Damit möchte man nur einen Teil updaten und nicht den gesamten Eintrag.
- Um im Frontend die Daten nochmal zu laden (also ein Update des Frontends) benutzt man `mutate`von useSWR (Daten revalidieren). Würde man nicht mit SWR arbeiten, dann müsste man nochmal fetchen

```js
// --- Backend: [id].js ---
...
if (request.method === "PUT") {
	const jokeData = request.body;
	await Joke.findByIdAndUpdate(id, jokeData);
	response.status(200).json({status: "Joke updated."});
}
```

```js
// --- Frontend: components/Joke/index.js ---
const { data, isLoading, mutate } = useSWR(`/api/jokes/${id}`)
...
async function handleEdit(event) {
	event.preventDefault();
	const formData = new FormData(event.target);
	const jokeData = Object.fromEntries(formData);

	const response = await fetch(`/api/jokes/${id}`, {
		method: "PUT",
		headers: {
			"Content-Type": "application/json",
		},
		body: JSON.stringify(jokeData),
	});

	if (response.ok) {
		mutate();
	}
}
```

## Delete

```js
// --- Backend: [id].js
...
if (request.method === "DELETE") {
	await Joke.findByIdAndDelete(id);
	response.status(200).json({ status: "deleted" });
}
```

```js
// --- Frontend: components/Joke/index.js
...
async function handleDelete() {
	await fetch(`/api/jokes/${id}`, {
		method: "DELETE",
	});
	router.push("/");
}
```

- Daten werden gelöscht, aber dann sollte man den User auch wieder umleiten (url), da es sonst sein kann, dass er sich immer noch den gelöschten Datensatz anschaut
