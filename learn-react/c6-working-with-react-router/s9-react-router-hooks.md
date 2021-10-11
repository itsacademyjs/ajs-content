
	React Router comes with some hooks that lets you manipulate and access the state of the router and perform navigation from inside your components. Here are the list of hooks

useHistory
useLocation
useParams
useRouteMatch

Let’s go through these hooks one by one.

useHistory 

 	React Router has two major dependencies. One of them is React, and the other is the history package. The history package provides several different implementations for managing session history. The history package has three DOM specific implementations, and React Router has three routers based on them, which we will see later in this session. 

Browser History - Helpful in managing history in browsers that support the HTML5 history API
Hash History - Helpful in managing history in old legacy browsers.
Memory History - An in-memory history useful in non-DOM environments (like React Native for example)

The history object has a few properties and methods like length, action (PUSH, REPLACE and POP), location, push (function), replace (function), go (function), goBack (function) and many more. You can find all the properties and methods of the history object in the documentation of the history package.

The useHistory hook gives you access to this history instance. Since the history object is mutable, you can change the hook directly when an event is triggered. Here is an example from the docs -

import { useHistory } from "react-router-dom";
 
function HomeButton() {
  let history = useHistory();
 
  function handleClick() {
    history.push("/home");
  }
 
  return (
    <button type="button" onClick={handleClick}>
      Go home
    </button>
  );
}

useLocation

	Just like useHistory, the useLocation hook lets you access the location object. The location object represents the current URL. The useLocation hook can be useful when you want to store a “pageview” event with the pathname to some web analytics tool. Here’s an example.

import React from "react";
import ReactDOM from "react-dom";
import {
  BrowserRouter as Router,
  Switch,
  useLocation
} from "react-router-dom";
 
function usePageViews() {
  let location = useLocation();
  React.useEffect(() => {
    ga.send([" ", location.pathname]);
  }, [location]);
}
 
function App() {
  usePageViews();
  return <Switch>...</Switch>;
}
 
ReactDOM.render(
  <Router>
    <App />
  </Router>,
  node
);

useParams

	useParams returns an object of key/value pairs of URL parameters.

useRouteMatch
	
	useRouteMatch hook attempts to match the current URL in the same way that a <Route> would without actually rendering a <Route>
