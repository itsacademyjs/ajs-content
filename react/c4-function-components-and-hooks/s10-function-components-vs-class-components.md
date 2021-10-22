Declaration
A functional component is just a plain JavaScript function that accepts props as an argument and returns JSX.

A class component is a ES6 class that extends React.Component class, whose render() function returns the JSX.

Hooks
Hooks were designed to address the lack of statefulness and lifecycle methods in functional components in older versions of React.

You cannot use hooks with class components.


State
The useState hook is used for maintaining states.

The this.setState function and this.state object are used for maintaining states.

Lifecycle
In functional components, the useEffect hook is used for implementing actions that happen at certain points in a component's lifecycle.

In class components, you can implement lifecycle methods that are called at certain points in a component’s lifecycle.