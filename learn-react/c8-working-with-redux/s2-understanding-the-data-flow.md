Redux is a pattern and library for managing and updating application state, using events called "actions". It serves as a centralized store for state that needs to be used across your entire application, with rules ensuring that the state can only be updated in a predictable fashion.

Let’s start by taking a look at a simple React counter app.

function Counter() {
 // State: a counter value
 const [counter, setCounter] = useState(0)
 
 // Action: code that causes an update to the state when something happens
 const increment = () => {
   setCounter(prevCounter => prevCounter + 1)
 }
 
 // View: the UI definition
 return (
   <div>
     Value: {counter} <button onClick={increment}>Increment</button>
   </div>
 )
}


This app, as you notice, has three things. It has a state, which can only be changed by an action, which can only be triggered from the view.

This is a “one-way” data flow, as shown in the diagram.


However, the simplicity can break down when we have multiple components that need to share and use the same state, especially if those components are located in different parts of the application. Sometimes this can be solved by "lifting state up" to parent components, but that doesn't always help.

One way to solve this is to extract the shared state from the components, and put it into a centralized location outside the component tree. With this, our component tree becomes a big "view", and any component can access the state or trigger actions, no matter where they are in the tree! 

