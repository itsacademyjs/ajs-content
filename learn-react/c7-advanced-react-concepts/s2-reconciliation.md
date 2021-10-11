In React, the React elements along with fibers form the virtual DOM. Fibers are internal objects that hold information about the tree. React Fiber is the reconciliation engine that does powers React 16+.

The render() function creates a tree of React elements. When the state or props change, the same render() function will return a different tree of React elements. The reconciliation engine is responsible to figure out how to efficiently update the real DOM to sync with the latest tree.

The reconciliation engine uses a heuristic algorithm with O(n) time complexity. The algorithm assumes that:
Two elements of different types will produce different trees.
The developer can provide a hint as to which child elements may be stable across different renders using the key prop.

The algorithm:
React first compares the two root elements.
If the DOM/component elements are of different types, React will build a new tree. The old tree is torn down by destroying the old DOM nodes. This is when the componentWillUnmount() life cycle method is invoked. When building up a new tree, new DOM nodes are inserted into the DOM. The UNSAFE_componentWillMount() life cycle method is invoked on the component instances and subsequently componentDidMount(). Any state associated with the old tree is lost.


If the DOM elements are of the same type, React compares the attributes of both, keeps the DOM node, and only updates the changed attributes. React takes this concept further for the style attribute, by modifying only updated style properties. React then recurses down the children nodes.


Component elements of the same type, the instance remains the same, so that state is maintained across renders. React updates the props of the to match the new element, and calls UNSAFE_componentWillReceiveProps(), UNSAFE_componentWillUpdate() and componentDidUpdate(). React then recurses down the children nodes.|


