# React Exercises

Exercise 1: Head over to www.babeljs.io and play around with Babel on the try-it-out page. See how many ES6 and ES7 features are converted into regular JS. Don’t forget to use the React preset.

Exercise 2: Take the output from the Babel Transpiler and replace the line where we define the JSX template with it. You should now be able to see your element on your HTML page. Try to create a containing component, or a parent component with several children components using React.createElement() function.

Exercise 3: There is a bug in the program below. It violates one of the rules of using States in React. Fix the bug. (HINT : Remember that state updates are asynchronous.)

```
import React, { Component } from 'react';
 
export default class Todo extends Component {
 constructor(props) {
   super(props);
   this.state = {
     items: [],
     checked: [],
     newTask: '',
   };
   this.changeNewText = this.changeNewText.bind(this);
  
 }
 
 changeNewText(event) {
   this.setState({
     newTask: event.target.value,
   });
   console.log(this.state.newTask);
 }
 
 handleAddItem() {
   this.setState({
     items: [...this.state.items, this.state.newTask],
     newTask: '',
   });
 }
 
 render() {
   return (
     <div>
       <input
         value={this.state.newTask}
         onChange={(event) => this.changeNewText(event)}
       />
       <button onClick={() => this.handleAddItem()}>Add New Item </button>
       <ul>
         {this.state.items.map((item, i) => (
           <li>
             <input type='checkbox' />
             {item}
           </li>
         ))}
       </ul>
     </div>
   );
 }
}
```

Exercise 3: Add a method that saves all the checked items in the state of the component. When an item is checked, the item should be added to the checked array and when it is unchecked, the item should be removed from the array. Remember that React states are immutable, so don’t try to mutate the array in your state. Instead, you would have to spread and rebuild an array for these operations.