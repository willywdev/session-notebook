# Styled Components I

## Basics

- No Classname conflicts anymore
- No more unused CSS Classes and Naming Conflicts
- Easier deletion of CSS since all CSS is in its components

```jsx
pnpm i styled-components

import styled from "styled-components"

const Heading = styled.h1`
	background-color: hotpink;
	color: white;
`;

const Button = styled.button`
	background-color: var(--primary-color);

	&:hover {
		background-color: red;
	}
`

<>
	<Heading>Hello World!</Heading>
	<Button>Click me!</Button>
</>
```

## Style other components

```jsx
const StyledLink = styled(Link)`
  text-decoration: none;
`;
```

## Global Styles

- create styles.js file in root
- if not setup, you need to config the \_document.js

```jsx
import { createGlobalStyle } from "styled-components";

export default createGlobalStyle`...`;
```
