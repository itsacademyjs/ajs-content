
Higher order components or HOCs are not part of the React API, rather they are a commonly used pattern for reusing component logic.

Generally speaking, we can write a higherOrderComponent function that takes a wrapped component as input and returns an enhanced component.

Just like a normal component takes in props, uses it inside it’s JSX and returns a UI, similarly, HOCs take in components and return another, more enhanced component.

You will notice that HOCs are very common in React third-party libraries, such as the connect() function in Redux.

Cross Cutting Concerns

Most modern applications have parts of the program depend on many other parts of the program. This kind of architecture does not cleanly fit with either object - oriented or procedural programming. HOCs can be used for code reuse in case of cross-cutting concerns. Let’s take an example from the React docs to understand this better.




import React, { Component } from "react";
 
const withCounter = (OriginalComponent) => {
 class NewComponent extends Component {
   constructor(props) {
     super(props);
 
     this.state = {
       count: 0,
     };
   }
 
   increment = () => {
     this.setState((prevState) => {
       return {
         count: prevState.count + 1,
       };
     });
   };
 
   render() {
     const { count } = this.state;
     return (
       <OriginalComponent
         count={count}
         increment={this.increment}
         {...this.props}
       />
     );
   }
 }
 return NewComponent;
};
 
export default withCounter;
 






import React, { Component } from "react";
import withCounter from "./withCounter";
 
class Counter1 extends Component {
 render() {
   const { count, increment, name } = this.props;
 
   return (
     <div>
       <button onClick={increment}>
         {name} Clicked {count} times
       </button>
     </div>
   );
 }
}
 
export default withCounter(Counter1);


import React, { Component } from "react";
import withCounter from "./withCounter";
 
class Counter2 extends Component {
 render() {
   const { count, increment, name } = this.props;
   return (
     <div>
       <h1 onMouseOver={increment}>
         {name} Clicked {count} times
       </h1>
     </div>
   );
 }
}
 
export default withCounter(Counter2);


