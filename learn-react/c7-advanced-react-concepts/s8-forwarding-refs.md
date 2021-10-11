In React, parents can only interact with children through propes. To modify a child, you re-render it with new props. However, there are a few cases where you need to modify a child without going through the entire cycle. For such situations, you can take advantage of refs.

React is primarily a declarative library. However, refs do not encourage declarative programming. Therefore, avoid them whenever you can. React provides a lot of brilliant ways for parent-children communication. So it is your responsibility to use refs as a last resort.

In class components, you can use the `createRef` function to create a ref object. You can access the ref value using the `current` attribute.

In functional components, you can use the `useRef` hook to create a ref object.

When you pass the ref object to a component through the `ref` prop, you can access the component’s node via `yourRef.current` . React consumes the prop and does not pass it to the child component. This is similar to how the key prop is never sent to child components.

class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.rootRef = React.createRef();
  }
  render() {
    return <div ref={this.rootRef} />;
  }
}
You need to remember the following rules when using refs to access nodes:
1. When ref prop is passed to a DOM component like `div` or `p`, the current attribute is assigned the actual DOM element.
2. When ref prop is passed to a class component like `Button` or `Card`, the instance of the class is assigned to current.
3. You cannot pass ref prop to functional components, because they don’t have instances!

Import React, {createRef} from ‘react’;
 
class App extends React.Component {
 
 constructor(props) {
   super(props);
 
   this.inputRef = createRef();
 }
 
 handleClick = () => {
   if (this.inputRef.current) {
     this.inputRef.current.focus();
     this.inputRef.current.select();
   }
 };
 
 render() {
   return (
     <div style={{ display: "flex", justifyContent: "center", alignItems: "center", width: "100%", height: "100vh" }}>
       <input ref={this.inputRef} />
       <button onClick={this.handleClick}>Bring me focus!</button>
     </div>
   );
 }
}
const App = () => {
 const inputRef = useRef();
 
 const handleClick = () => {
   if (inputRef.current) {
     inputRef.current.focus();
     inputRef.current.select();
   }
 };
 
   return (
     <div style={{ display: "flex", justifyContent: "center", alignItems: "center", width: "100%", height: "100vh" }}>
       <input ref={inputRef} />
       <button onClick={handleClick}>Bring me focus!</button>
     </div>
   );
}



