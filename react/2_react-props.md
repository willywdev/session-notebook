# React Props

- Flexibilität für die Komponenten (Funktionen)
- Props sind die Parameter die wir in eine Komponente geben
- In JSX übergeben wir Props ähnlich wie bei HTML die Attribute
- Leerzeichen in JSX: `{" "}`
- React Komponenten sind wiederverwendbare Funktionen, die UI-Elemente erzeugen
- React Komponenten werden anfangs groß geschrieben
- React Komponenten werden in JSX Markup geschrieben
- Um React Komponenten noch flexibler und wiederverwendbarer zu machen, nutzen wir **Props**
- Einseitiger Datenfluss. Geht nur in eine Richtung (Parent -> Kids)

```jsx
export default function App() {
  return (
    <div>
      <Animal sound="Meow" emoji="🐱" name="A cat" />
      <Animal sound="Woof" emoji="🐶" name="A dog" />
      <Animal sound="Peep" emoji="🐭" name="A mouse" />
    </div>
  );
}

function Animal(props) {
  return (
    <div>
      {props.sound}{" "}
      <span role="img" aria-label={props.name}>
        {props.emoji}
      </span>
    </div>
  );
}
```

## Optimierung von Props mit Destructuring

```jsx
// ------------DESTRUCTURING-------------------------- \\
function Animal({ sound, emoji, name }) {
  // --------------------------------------------------- \\

  return (
    <div>
      {sound}{" "}
      <span role="img" aria-label={name}>
        {emoji}
      </span>
    </div>
  );
}
```

## Funktionen als Props übergeben ("Click"-EventListener)

```jsx
function Animal({ sound, emoji, name, onPet }) {
  return (
    <div onClick={onPet}>
      {sound}{" "}
      <span role="img" aria-label={name}>
        {emoji}
      </span>
    </div>
  );
}

export default function App() {
  function handlePets() {
    console.log("Thank you!");
  }

  return (
    <div>
      <Animal sound="Meow" emoji="🐱" name="A cat" onPet={handlePet} />
      <Animal sound="Woof" emoji="🐶" name="A dog" onPet={handlePet} />
      <Animal sound="Peep" emoji="🐭" name="A mouse" onPet={handlePet} />
    </div>
  );
}
```

### EventListener

`onClick={}` , `onSubmit={}`, `onChange={}`

## Naming Convention für Übergabe von Funktionen

Als Prop übergeben: `onPet`
Als Funktion deklarieren: `handlePet`

## Conditional Rendering (Ternary Operator)

```jsx
function Animal({ sound, emoji, name, onPet, isHungry }) {
	return (
		<div onClick={onPet}>
	// --------------- Ternary Operator ----------------- \\
			{isHungry ? "Feed me!" : sound}{" "}
	// -------------------------------------------------- \\
			<span role="img" aria-label={name}>
				{emoji}
			</span>
		</div>
	)
}

export default function App() {
	function handlePets() {
		console.log("Thank you!");
	}

	return (
		<div>
			<Animal sound="Meow" emoji="🐱" name="A cat" onPet={handlePet}/ isHungry={false}>
			<Animal sound="Woof" emoji="🐶" name="A dog" onPet={handlePet}/>
			<Animal sound="Peep" emoji="🐭" name="A mouse" onPet={handlePet} isHungry={true}/>
		</div>
	)
}
```
