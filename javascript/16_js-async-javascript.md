# Async JavaScript

- Manche Operationen brauchen gewisse Zeit. Selbst eine halbe Sekunde ist relativ lang. Diese nennt man Asynchrone Operationen
- Als Webentwickler: Hauptsächlich Daten fetchen (APIs)
- Während eine solche Operation läuft, läuft der Code trotzdem weiter. Deswegen brauchen wir asynchrone Funktionen
- JavaScript ist Single-Thread (nur eine Aufgabe auf einmal)

## Promises und `.then()`

- Ein Promise wird immer als Promise returned.
- "Versprechen", dass wenn die asynchrone Operation fertig ist, dass es dann weiter geht
- Verschiedene Stadien: `<pending>` , `<resolved>` , `<rejected>`
- Promises haben verschiedene Methoden: `.then()`
- `.then()` = Wenn Promise resolved, **dann** mache jenes.

```javascript
const soccerAnimation = animateBall(soccer);
soccerAnimation
  .then(() => {
    console.log("soccer animation finished");
    const basketballAnimation = animateBall(basketball);
    return basketballAnimation;
  })
  .then(() => {
    console.log("basketball animation finished");
  });
```

Man kann `.then()` auch tiefer verschachteln. Aber daraus wird eine Callback-Hell.
Deswegen:

```javascript
animateButton.addEventListener("click", async () => {
  const soccerAnimation = animateBall(soccer);
  // Promise auffangen
  await soccerAnimation;
  // Warten bis `soccerAnimation` fertig, dann:
  console.log("soccer animation finished");

  const tennisAnimation = animateBall(tennis);
  await tennisAnimation;
  console.log("tennis animation finished");

  ...
});
```

- `.then()` steht nur zur Verfügung, wenn man ein Promise hat.

## Neuere Variante: `async` und `await`

- Neuere Schreibweise von `.then()`
- Gleiches Beispiel:

```javascript
animateButton.addEventListener("click", async () => {
  await animateBall(soccer);
  console.log("soccer animation finished");

  await animateBall(basketball);
  console.log("basketball animation finished");

  await animateBall(football);
  console.log("football animation finished");

  await animateBall(tennis);
  console.log("tennis animation finished");
});
```

- ! Async und Await funktionieren nur mit Promises !
- Das ganze in noch kürzer:

```javascript
animateButton.addEventListener("click", async () => {
  await animateBall(soccer);
  await animateBall(basketball);
  await animateBall(football);
  await animateBall(tennis);
});
```

## `Promise.all()`

- Wenn man mehrere Promises hat und auf diese warten muss, benutzt man `Promise.all()`
- Promise.all nimmt ein Array von Promises an und return die Results in einem Array

```javascript
async function myAsyncFunction() {
  try {
    const values = await Promise.all([
      functionThatReturnsAPromise1(),
      functionThatReturnsAPromise2(),
      functionThatReturnsAPromise3(),
    ]);
    console.log(values); // [value1, value2, value3]
  } catch (error) {
    console.error(error);
  }
}
```
