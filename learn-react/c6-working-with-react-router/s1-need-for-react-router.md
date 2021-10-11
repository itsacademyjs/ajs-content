	Let’s start this session by understanding why we need React Router in the first place. Most apps you see on the internet today don’t have multiple pages. They are SPAs - or Single Page Applications. 

They seem like they have multiple pages, but what is actually happening is that they are rendering different components and views based on the current URL in the browser. So the components rendered for the home page will be different, and it will be defined in the route “/”, and the components rendered for, say the about page will be defined in the route “/about”.

Now that we know what React Router actually does, let’s get our hands dirty and try out the React Router DOM.

You can start using React Router in your project by adding it using NPM or yarn using -

npm install react-router-dom

yarn add react-router-dom

In this session, in order to demonstrate React Router, we will build a simple app that uses Routing.

Open your bare bones CRA app and go to the index.js file. We need to wrap the App component inside the <BrowserRouter> component as shown below.



import React from "react";
import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import reportWebVitals from "./reportWebVitals";
import { BrowserRouter } from "react-router-dom";
 
ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
 
// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
 


The <BrowserRouter> component handles the logic of rendering certain components based on the route. Now, let’s head over to your app.js file. 

Here, we will be using the <Switch> component which makes sure that only one component is rendered at a time. 

It also lets you default to an Error component which we shall do later in this session.

```javascript
import "./App.css";
import { Switch } from "react-router-dom";
 
function App() {
  return (
    <div className="App">
      <Switch>
        ...
      </Switch>
    </div>
  );
}
 
export default App;
```