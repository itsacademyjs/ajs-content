Passing props from a parent component to a child component is very straightforward. But how would you pass props from a child component to a parent component? This is a little different. Here’s how it’s implemented.

Well, here’s how we do it. We first create a function in the parent component that sets that value of one of its props or does anything else.

Now, we pass this function as props to our child component.

Inside our child component, we have access to this callback function, where we can send some data to it, and it will use this data to set some props in the parent. We can now call this callback function available to use in our props and send whatever data we need to send from the child component to the parent component.

Here is a template example of how that’s done. Please note, this is a very important pattern in React and used very frequently:

```javascript
import "./App.css";
 
const MyButton = (props) => {
 const handleClick = () => {
   const result = parseInt(Math.random() * 100);
   props.onResult(result);
 };
 
 // Child
 return (
   <button onClick={handleClick} className="my-button">
     Click me!
   </button>
 );
};
 
const Container = () => {
 const showResult = (result) => {
   alert("The random number is " + result);
 }
 
 return (
   <div className="container">
     <MyButton onResult={showResult} />
   </div>
 );
};
 
export default Container;
 
// When the user clicks on the button in my child, -- solved
// the child computes a 1+2 -- solved
// the result is sent to my parent.
// The parent should then show the result as an alert.
 
 
 
// parent                            result
// \                                   /
//   callback via props              /
//     \                           /
//     child                     /
//       \ callback()          /
 















import React from 'react';
 
class App extends React.Component {
 
 onResult(result) {
   alert(result);
 }
 
 render() {
   return <Calculator a={10} b={5} onResult={this.onResult} />;
 }
}
 
class Calculator extends React.Component {
 
 constructor(props) {
   super(props);
 
   this.handleClick = this.handleClick.bind(this);
 }
 
 handleClick() {
   const a = this.props.a;
   const b = this.props.b;
   const result = (a * a) + (b * b) + (2 * a * b);
  
   this.props.onResult(result);
 }
 
 render() {
   const ref = this.handleClick;
   return <div>
       <button onClick={ref}>Click me to show the result</button>
     </div>
 }
}

export default App;
```