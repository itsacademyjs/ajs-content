Components allow you to split your UI into independent and reusable pieces. They are like functions. They accept arbitrary inputs called props and return React elements that need to be rendered on screen. There are two ways to implement components in React: classes and functions. You’ve already seen how to implement class components. In this section, you will learn how to implement components using functions (functional components).

The simplest way to create a component is to write a function:
function Message() {
   return <h1>Hello, world!</h1>;
 }
 

The equivalent class component would be:
class Message extends React.Component {
   render() {
       return <h1>Hello, world!</h1>;
   }
}
 


Your functional component can access props by accepting the props object as an argument like this:
function Message(props) {
   return <h1>Hello, {props.name}</h1>;
}


The equivalent class component would be:
class Message extends React.Component {
   render() {
     return <h1>Hello, {this.props.name}</h1>;
   }
}
