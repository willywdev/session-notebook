# Backend Create

## RESTful: CRUD Operationen

Create (POST)
Read (GET)
Update (PUT)
Delete (DELETE)

REST = Standardisierung, wie man APIs aufbaut

## CREATE (POST)

- Daten des Bodys sind notwendig. Die kriegen wir von "request"

```js
// --- Backend --- //
// POST Methode ist automatisch, sobald Daten mitgeschickt werden
if (request.method === "POST") {
  // beim senden der daten kann schiefgehen, deswegen:
  try {
    const jokeData = request.body;
    // request wird mitgeschickt, wenn die api aufgerufen wird
    // bei POST ist dieser auch gefüllt
    await Joke.create(jokeData);
    // mongoose methode um daten auf der db zu erstellen
    response.status(201).json({ status: "Joke created" });
  } catch (error) {
    console.log(error);
    response.status(400).json({ error: error.message });
  }
}
```

```jsx
// --- Frontend --- //
// --- JokeForm.js --- //
export default function JokeForm() {
  // Daten werden nicht direkt angezeigt, weil kein State vorhanden:
  // useSWR gibt uns "mutate" dafür
  const { mutate } = useSWR("/api/jokes");

  async function handleSubmit(event) {
    event.preventDefault();
    const formData = new FormData(event.target);
    const jokeData = Object.fromEntries(formData);
    // Output: joke: String
    const response = await fetch("/api/jokes", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(jokeData),
    });
    // fetch ist nicht nur um Daten zu bekommen, sondern auch um diese
    // zu verschicken. Dafür nimmt man als zweiten Parameter ein Objekt
    // So ein Objekt kann so nicht verschickt werden, also -> String
    if (response.ok) {
      mutate();
      // sorgt für einen Rerender, wenn sich etwas an bereits
      // gefetchten Daten ändert. z.B. bei einem FormSubmit
    }
  }

  return (
    <form onSubmit={handleSubmit}>
      <label htmlFor="joke-input">Enter Joke:</label>
      <input type="text" id="joke-input" name="joke" required />
      <button type="submit">Submit</button>
    </form>
  );
}
```
