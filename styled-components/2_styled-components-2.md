# Styled Components II

Global Styles: `styles.js` in root

## Styled Components with Props

- Props können auch in Styled Components gegeben werden, um z.B. conditional styling umzusetzen

```jsx
import styled from "styled-components";

export default function HomePage() {
	return (
		<h1>Styled Components with Props</h1>
		<h2>Props and the ternary</h2>
		<FlexContainer>
			<Button>Normal Button</button>
			<Button $color="danger">Danger Button</button>
// ----------------- ^ Giving prop to styled component ------ \\
		</FlexContainer>
	)
}

const Button = styled.button`
	border: none;
	cursor: pointer;
	padding: 1rem;
	color: white;

	background-color: var(${({ $color }) => $color === "danger" ? "--color-danger" : "--color-primary"})

// --- ^ Getting and using the props --- \\

	&:hover {
		color: var(--color-primary);
		background-color: var(--color-secondary);
	}
`
```

- Prefix with a $ Sign
- Give prop to styled component
- Prop not visible in DOM

## Another way with css from styled-components

```jsx
import styled, { css } from "styled-components";

...
<h2>Props for more than one css property</h2>
<FlexContainer>
	<Button $variant="text">Im a Button - Text</Button>
	<Button $variant="outlined">Im a Button - Outlined</Button>
	<Button $variant="contained">Im a Button - Contained</Button>
</FlexContainer>
...

const Button = styled.button`
	border: none;
	cursor: pointer;
	padding: 1rem;
	color: white;

	background-color: var(${({ $color }) => $color === "danger" ? "--color-					  danger" : "--color-primary"})

	${(props) => props.$variant === "text" && css`
			background-color: transparent;
			color: black;
	`}

	&:hover {
		color: var(--color-primary);
		background-color: var(--color-secondary);
	}
`

```

- using "css" from styled components
- callback function with ternarys

## Make styled components reusable (export)

```jsx
// New file: Button.styled.jsx

import styled, { css } from "styled-components";

const Button = styled.button`
... //styled component
`;

export default Button;
```

## File Ending for styled components:

`*.styled.js *.styled.jsx`
