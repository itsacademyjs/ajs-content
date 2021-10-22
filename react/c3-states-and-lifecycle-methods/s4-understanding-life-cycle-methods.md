	
If your application has a lot of components, you would have noticed that it’s important to free up resources once a component is no longer required. 

React Lifecycle methods are methods that are called on certain important points throughout the lifecycle of a component. These points are - the birth or the mounting of your component to the DOM, the growth or the updating of your component on the DOM, and finally the death, or the unmounting of your component from the DOM. Now that we know about the series of events, let’s take a deep dive into some React lifecycle methods.

import React from "react";
 
class Student extends React.Component {
 
 constructor(props) {
     super(props);
     console.log("I was constructed");
 }
 
 componentWillMount() {
   console.log("I'm about to be mounted");
 }
 
 componentDidMount() {
   console.log("I'm mounted!");
 }
 
 render() {
   console.log("I'm about to be rendered");
     return <div>
     </div>
 }
}
 
export default Student;
