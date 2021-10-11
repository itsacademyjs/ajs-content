Here are some rules that you should keep in mind while using and modifying states in React: 
Do not modify the state directly. Use this.setState instead
React state updates may be asynchronous. This means that React may decide to batch several this.setState()’s together. So using this.state.value inside your this.setState may or may not use the initial value that you hoped to use.
State updates are merged.
States need to be immutable.

Let’s talk about each of these rules one by one.

The first rule is that you should not directly change the values in your state. Instead, you should use this.setState() method. The constructor of your class is the only place you can set values for this.state directly.

// Wrong
this.state.comment = 'Hello';
 
// Correct
this.setState({comment: 'Hello'});

The reason behind this is if you directly mutate your state and then later use this.setState(), it might replace the mutation you made earlier.

The second rule is that React state updates maybe asynchronous. React may batch multiple setState() calls into a single setState() call. Because this.state may be updated asynchronously, relying on their values for calculating the next state is not really a good idea. To fix it, use a second form of setState(). The second form of setState() accepts a function rather than an object. That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument:

// Wrong
this.setState({
 counter: this.state.counter + this.props.increment,
});
 
// Correct
this.setState(function(state, props) {
 return {
   counter: state.counter + props.increment
 };
});


	The third rule is pretty straightforward. If your state has different variables, you can update them independently as shown below:

 componentDidMount() {
   fetchPosts().then(response => {
     this.setState({
       posts: response.posts
     });
   });
 
   fetchComments().then(response => {
     this.setState({
       comments: response.comments
     });
   });
 }


Your current todo app is not functional, because it doesn’t use states. Let’s just add states to this component. A todo app will have three states. First, you would need an array of todo items that you render as a list. You can append items to this list and you can also remove items from this list. You would need a second state to store the index of the item which is currently selected. You would also need a third state to hold the value the user inputs in the text input box of your todo app.

Once we add these three states, your todo component should look something like this - 

 
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

Assignment 3A: There is a bug in the program above. It violates one of the rules of using States in React. Fix the bug. (HINT : Remember that state updates are asynchronous.)

Assignment 3B: Add a method that saves all the checked items in the state of the component. When an item is checked, the item should be added to the checked array and when it is unchecked, the item should be removed from the array. Remember that React states are immutable, so don’t try to mutate the array in your state. Instead, you would have to spread and rebuild an array for these operations.

Now let’s give this todo app a few more features. React offers you two special methods on the component class to run some code when the component class mounts and unmounts. We'll talk more about these lifecycle methods in the next section.