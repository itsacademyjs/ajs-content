Don’t call hooks inside loops, conditions, nested functions. Only call hooks from at the top level of a React Function. There is a very specific reason for this. Having all your hooks at the top level will ensure that the Hooks are called in the same order each time a component renders. We will learn more about why this is so important in an example below.
Don’t call hooks from regular Javascript functions. Only call hooks from react functional components.

