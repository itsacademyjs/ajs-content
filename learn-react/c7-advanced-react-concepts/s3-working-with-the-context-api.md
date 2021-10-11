As we have already seen in previous sections, we can pass down data from parent to children through props. However, props are not suitable for passing down data when your components are deeply nested. For example, let’s say you have an hierarchy like this:

<A>
   <B>
     <C />
   </B>
</A>

If you want to pass data from A to C, you first need to pass the prop to B from A, and then B passes down the prop to C. Now let’s scale things up. What if your destination component was nested 10 levels deep? It would be cumbersome to pass down the prop each level! This is the problem that the Context API was designed to address.

The Context API is designed to broadcast data that is considered global for a given tree. Whenever the data in the context is changed, the receiving components automatically have access to the new data. Any node within the tree can access the data without its parent actually passing it. So what kind of data are we talking about? It could be anything, examples include, but not limited to, authenticated user session, theme,  preferences, and so on.

To create a context object, you use the React.createContext function. It accepts a default value and returns the context object. You can access the Provider component through the context object. The Provider component allows you to pass the context data through the value prop.

So what’s the difference between passing the default value to createContext and passing the value prop to the Provider component? When your subscribing component tries to access the context data, React tries to find the nearest Provider component in the hierarchy whilst traversing towards the root of the tree. If found, the data passed to the value prop is given to the subscribing component. Otherwise the default value provided to createContext is given to the subscribing component.

Here’s an example:
const MyContext = React.createContext(defaultValue);

const MyComponent = () => {
    return (
        <MyContext.Provider value={...}>
            ...
        </MyContext.Provider>
    );
}

If you are working with class components, there are two ways to access the context data:
MyComponent.contextType = MyContext
With this technique, this.context is assigned the context data. The caveat with this technique is that you cannot access multiple contexts this way.

<MyContext.Consumer>{(value) => … }</MyContext.Consumer>
With this technique, you provide a function as the child to the MyContext.Consumer component. The function is invoked with the context data as its first argument. The function is responsible to return a React node.

If you are working with functional components, you can use the useContext hook to access the context data.
const data = useContext(MyContext);


// App.js
 
import React from "react";
 
import ThemeContext from "./ThemeContext";
import { darkTheme } from "./theme";
import Card from "./Card";
 
const App = () => (
 <ThemeContext.Provider value={darkTheme}>
   <Card title="My Card" />
 </ThemeContext.Provider>
);
 
export default App;

// Card.js
 
import React from "react";
 
import ThemeContext from "./ThemeContext";
import Actions from "./Actions";
 
class Card extends React.Component {
 render() {
   return (
     <div>
       <h1 style={{ color: this.context.cardTitleColor }}>{this.props.title}</h1>
       <Actions />
     </div>
   );
 }
}
 
Card.contextType = ThemeContext;
 
export default Card;

// Actions.js
 
import React from "react";
 
import Button from "./Button";
 
const Actions = (props) => {
 return (
   <div>
     <Button title=”Okay” />
     <Button title=”Cancel” />
   </div>
 );
};
export default Actions;
 
// Button.js
 
import React, { useContext } from "react";
 
import ThemeContext from "./ThemeContext";
 
const Button = (props) => {
 const theme = useContext(ThemeContext);
 
 return (
   <button
     style={{
       color: theme.buttonTextColor,
       background: theme.buttonColor,
     }}
   >
     {props.title}
   </button>
 );
};
 
export default Button;
 

// theme.js
 
export const darkTheme = {
   cardTitleColor: "black",
   buttonColor: "black",
   buttonTextColor: "white",
 };
 
export const lightTheme = {
   cardTitleColor: "black",
   buttonColor: "white",
   buttonTextColor: "black"
};

// ThemeContext.js
 
import React from "react";
 
import { lightTheme } from "./theme";
 
const ThemeContext = React.createContext(lightTheme);
 
export default ThemeContext;
