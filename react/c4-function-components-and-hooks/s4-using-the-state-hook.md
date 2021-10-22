useState allows you to add a local state to your functional component. React will preserve this state between re-renders. useState returns an array with two elements: the current state value and a function that lets you update it. It’s similar to this.setState in a class, except it doesn’t merge the old and new state together.

You can pass the initial state value as an argument to useState, which is used only during the first render. Unlike this.state, the state here doesn’t have to be an object — although it can be if you want.

import React, { useState } from 'react';
 
function Counter() {
 const [count, setCount] = useState(0);
 
 function updateCount() {
   setCount(count + 1);
 }
 
 return (
   <div>
     <p>You clicked {count} times</p>
     <button onClick={updateCount}>
       Click me
     </button>
   </div>);
}

Multiple states in class components:
class ClassComponent extends React.Component {
 constructor(props) {
   super(props);
 
   this.state = {
     firstName: "",
     lastName: "",
   };
   this.handleFirstName = this.handleFirstName.bind(this);
   this.handleLastName = this.handleLastName.bind(this);
 }
 
 handleFirstName(event) {
   this.setState({ firstName: event.target.value });
 }
 
 handleLastName(event) {
   this.setState({ lastName: event.target.value });
 }
 
 render() {
   return (
     <div>
       <p>Hello, {this.state.firstName} {this.state.lastName}!</p>
       <input value={this.state.firstName} onChange={this.handleFirstName} />
       <input value={this.state.lastName} onChange={this.handleLastName} />
     </div>
   )
 }
}

To create multiple states, you just need to call useState multiple times like this:
import React, { useState } from "react";
 
function Name() {
 const [firstName, setFirstName] = useState("");
 const [lastName, setLastName] = useState("");
 
 function updateFirstName(event) {
   setFirstName(event.target.value);
 }
 
 function updateLastName(event) {
   setLastName(event.target.value);
 }
 
 return (
   <div>
     {firstName && lastName && (
       <p>
         Hi, {firstName} {lastName}!
       </p>
     )}
     <input value={firstName} onChange={updateFirstName} />
     <input value={lastName} onChange={updateLastName} />
   </div>
 );
}
 
export default Name;
