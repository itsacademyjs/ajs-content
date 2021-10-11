You can create a React class component by extending Component class that is present in the React variable. Here is an example of a valid React class component: 

```javascript
import { Component } from "react";

class Header extends Component {

	render() {
		return <p>Hello, world!</p>;
	}
}
```

A class component must implement the `render()` method, which returns a single root JSX
element. The root can have any number of children and nest elements to any depth, as
long as you a single root JSX element.

The convention for naming classes is to use PascalCase, where the first letter of every word
is uppercase. It is merely a convention and that a lowercase first letter is perfectly valid.

However, with React components that's no longer the case. React enforces that at least the
first letter of the identifier should be uppercase. If you have a lower case first letter
and you try to use that down here it is not going to fail it's just not going to render
your component. The uppercase first letter is how React differentiates between an HTML element
like `div` and other React components.
