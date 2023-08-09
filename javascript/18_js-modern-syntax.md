# JavaScript Modern Syntax

JavaScript wird immer weiter entwickelt = Neue Versionen
**ECMAScript**

## Destructuring Assignment

```javascript
const tree = {
  name: "oak",
  age: 1200,
  scientificName: "quercus",
};
```

- Von einem Objekt / Array die einzelnen Keys / Properties extrahieren
- Ursprüngliches Objekt bleibt unverändert

```javascript
// BISHER:
const name = tree.name;
const age = tree.age;
const scientificName = tree.scientificName;

// MIT DESTRUCTURING + OBJECT:
const { name, age, scientificName } = tree;

// UMBENENNEN + DESTRUCTURING:
const { name: currywurst, age: wurstbrot, scientificName: pommes } = tree;

// DEFAULT WERT (wird überschrieben, sobald Key im echten Objekt dazukommt) :
const { keepsLeavesInWinter = false } = tree;

// Noch eine Möglichkeit (... gibt den Rest zurück):
const { name, ...information } = tree;

// ---------------------------------------------------------------

// MIT DESTRUCTURING + ARRAY:
const animals = ["Lion", "Tiger", "Penguin", "Bear", "Whale"];

const [eins, zwei, drei] = animals;

// Index ignorieren:
const [eins, , drei] = animals;
```

## Rest Syntax

- Sinnvoll, wenn man nicht weiß, wieviele Parameter übergeben werden
- Nimmt alle Argumente / Parameter und macht daraus ein **Array**
- Das `...parameter` muss immer als letztes stehen

```javascript
function showZooAnimals(...allAnimals) {
 console.log(allAnimals);
 return `My zoo consists of the following animals:
   ${allAnimals.join(", ")}.`:
}
console.log(showZooAnimals("Monkey", "Tiger", "Bear", "Lion", "Elephant", "Fish", "Penguin", "Deer"));
```

## Spread Syntax

- Gegenteil von Rest Syntax
- Nimmt sich alle verbliebenen Elemente und **spreaded** sie auseinander

```javascript
const [lion, tiger, penguin, ...otherAnimals] = animals;
/* Output: ["Bear", "Whale"] */

console.log(...otherAnimals);
/* Output: "Bear", "Whale" */

/* ----------------------------------------------------------- */
// Neue Variable zu einem Array hinzufügen:
const animalFood = ["Meat", "Apple", "Banana", "Carrot"];
const newAnimalFood = "Fish";

const allAnimalFood = [...animalFood, newAnimalFood];
console.log(allAnimalFood);
/* Output: [ "Meat", "Apple", "Banana", "Carrot", "Fish" ]

/* ----------------------------------------------------------- */
// Zwei Arrays zusammenfügen:
const allMyAnimals = [...animals, ...animalFood];
```
