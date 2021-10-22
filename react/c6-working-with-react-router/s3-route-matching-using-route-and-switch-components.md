Now, we will start adding the <Route> tag inside this <Switch> component. Each <Route> element is provided with two things. First, the path, and second, the component to be loaded in a particular path.

Here is an example of using the <Route> tag.

<Route path='/' component={Home} />

Let’s go ahead and add a few routes inside our switch.

import "./App.css";
import { Route, Switch } from "react-router-dom";
 
function App() {
  return (
    <div className="App">
      <Switch>
        <Route path="/" component={Home} exact={true} />
        <Route path="/about" component={About} />
      </Switch>
    </div>
  );
}
 
export default App;

You might notice that the Home route looks a little different. It has the exact attribute set to true. You can guess the reason behind this. 

All the other URLs also contain the “/” character. By adding the exact attribute, we are telling our React App to look for the exact match of “/”, and only then render the Home component. Otherwise, the app loads the first component that matches “/”.

All you need to do now is import your Home and About components and you are good to go. You can test out the result in the browser by typing the URLs.

As you might have noticed, this is not very convenient. You need a way to navigate through your app using a navigable interface, say something like a NavBar, which we will make later in this session.
