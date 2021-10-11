Hooks are special functions that allow you to use state and other React features with functional components.

Problems hooks solve:
Class components do not offer a primitive way to share reusable state logic between components. For example, connecting a component to a store in Redux you will need to use patterns like render props and higher-order components. But these patterns require you to restructure your components which is bad for readability. Also, they cause “wrapper hell” of components surrounded by layers of providers, consumers, higher-order components, render props, and other abstractions.
With class components, they start out simple but grow into an unmanageable mess of stateful logic and side effects. For example, components might perform some data fetching in componentDidMount and componentDidUpdate. However, the same componentDidMount method might also contain some unrelated logic that sets up event listeners, with cleanup performed in componentWillUnmount. Mutually related code that changes together gets split apart, but completely unrelated code ends up combined in a single method. This makes it too easy to introduce bugs and inconsistencies.
JavaScript classes are a mess!
1. No ‘this’ reference
It’s always an advantage to not worry about ‘this’ when you’re working with Javascript. For one, you do not have to bind your functions, which is a confusing concept to wrap to begin with.

2. Fewer lines
Functional components transpile down to less code than class components, which means functional components help in producing smaller bundles.

3. Easier to work with
Functional components are easier to read, easier to understand, easier to reason about, and easier to test.
