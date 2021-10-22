ComponentDidMount Method

The componentDidMount() method runs after the component output has been rendered to the DOM. You could use the ComponentDidMount method in your Todo app too! For example, to add a timer as soon as the page is loaded. (Should we do this?)

componentDidMount() {
      // Do something when your component is mounted
}

ComponentWillUnmount Method

The componentWillUnmountMethod will be code that will be executed when your component is removed from the DOM. Notice how our Todo component renders a list when we add a new item. To demonstrate componentWillUnmount, you can make your list into a separate component, add a delete button to your app that removes the entire list and log out something from the componentWillUnmount method.

import React from "react";
 
class App extends React.Component {
 
 constructor(props) {
   super(props);
 
   this.state = {
     seconds: 0
   };
   this.updateSeconds = this.updateSeconds.bind(this);
 }
 
 componentDidMount() {
   this.reference = setInterval(this.updateSeconds, 1000);
 }
 
 componentWillUnmount() {
   clearInterval(this.reference);
 }
 
 updateSeconds() {
   this.setState(function (previousState) {
     return {
       seconds: previousState.seconds + 1
     };
   });
 }
 
 render() {
   return <div style={{ display: "flex", justifyContent: "center", alignItems: "center", fontSize: 80, height: "100vh" }}>
     {this.state.seconds}
   </div>
 }
}
 
export default App;
