import React, { Component } from "react";
 
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
 
export default Counter1;


import React, { Component } from "react";
 
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
 
export default Counter2;




import React, { Component } from "react";
 
export default class WrapperComponent extends Component {
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
   return <div>{this.props.render(this.state.count, this.increment)}</div>;
 }
}
 


import "./App.css";
import Counter1 from "./components/Counter1";
import Counter2 from "./components/Counter2";
import WrapperComponent from "./components/WrapperComponent";
 
function App() {
 return (
   <div className="App">
     <WrapperComponent
       render={(count, increment) => (
         <Counter1 count={count} increment={increment} />
       )}
     />
     <WrapperComponent
       render={(count, increment) => (
         <Counter2 count={count} increment={increment} />
       )}
     />
   </div>
 );
}
 
export default App;
 
 

