# HTML Forms

## HTML Forms

Formulare in HTML ermöglichen es den Benutzern, Daten an den Server zu senden. Sie bestehen aus verschiedenen Formularelementen wie Textfeldern, Auswahllisten, Checkboxen, Radiobuttons und Buttons.

### `<form>`-Element

Das `<form>`-Element wird verwendet, um ein Formular zu erstellen. Es enthält alle Formularelemente und definiert die Datenübermittlung an den Server.

Beispiel:

```html
<form action="/submit" method="post">
  <!-- Form elements go here -->
</form>
```

### `<input>`-Element

Das `<input>`-Element wird verwendet, um verschiedene Arten von Eingabefeldern zu erstellen, z. B. Textfelder, Passwortfelder, Checkboxen, Radiobuttons und mehr.

Beispiel:

```html
<input type="text" name="username" id="username" />
<input type="password" name="password" id="password" />
<input type="checkbox" name="subscribe" id="subscribe" />
<input type="radio" name="gender" value="male" id="male" />
<input type="radio" name="gender" value="female" id="female" />
```

### `<label>`-Element

Das `<label>`-Element wird verwendet, um einen lesbaren Text für ein Eingabefeld zu erstellen. Es wird normalerweise mit dem `for`-Attribut mit dem `id` des zugehörigen `<input>`-Elements verknüpft.

Beispiel:

```html
<label for="username">Username:</label>
<input type="text" name="username" id="username" />
```

### `<select>` und `<option>`-Elemente

Das `<select>`-Element wird verwendet, um ein Dropdown-Menü zu erstellen. Es enthält mehrere `<option>`-Elemente, aus denen der Benutzer auswählen kann.

Beispiel:

```html
<select name="country" id="country">
  <option value="usa">USA</option>
  <option value="uk">UK</option>
  <option value="germany">Germany</option>
</select>
```

## Fieldset und Legend

Das `<fieldset>`-Element wird verwendet, um Formularelemente zu gruppieren, die zusammengehören. Es hilft dabei, ein Formular in Abschnitte zu unterteilen und die Struktur zu organisieren.

Das `<legend>`-Element wird innerhalb des `<fieldset>`-Elements verwendet, um eine Überschrift oder eine Legende für das Feldset anzugeben.

Beispiel:

```html
<fieldset>
  <legend>Personal Information</legend>
  <!-- Form elements go here -->
</fieldset>
```

## Accessibility in Forms

Accessibility, also die Barrierefreiheit, ist ein wichtiger Aspekt bei der Gestaltung von Formularen. Es ist wichtig, sicherzustellen, dass Formulare auch von Menschen mit Behinderungen gut bedient werden können, insbesondere von denen, die Screenreader verwenden.

Um die Grund-Accessibility in Forms zu gewährleisten, sollten `<label>`-Elemente immer mit den zugehörigen `<input>`- oder `<select>`-Elementen verknüpft sein. Dazu wird das `for`-Attribut des `<label>`-Elements mit dem `id`-Attribut des `<input>`- oder `<select>`-Elements verbunden.

Es ist auch möglich, die Verknüpfung umzukehren, indem das `<input>`- oder `<select>`-Element mit dem `aria-labelledby`-Attribut verknüpft wird und das `id`-Attribut des `<input>`- oder `<select>`-Elements mit dem Wert des `aria-labelledby`-Attributs des `<label>`-Elements.

Zusätzlich zu den Labels sollten Formularelemente durch das Hinzufügen von `aria-describedby`-Attributen mit zugehörigen `<p>`-Elementen beschrieben werden, um zusätzliche Informationen bereitzustellen.

Barrierefreie Formulare sind wichtig, um die Benutzererfahrung für alle Benutzer zu verbessern und sicherzustellen, dass jeder, unabhängig von seinen Fähigkeiten, das Formular problemlos ausfüllen kann.
