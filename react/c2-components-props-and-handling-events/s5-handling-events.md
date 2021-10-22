Let’s start by understanding what events actually are. Events are something that a browser does, or something a user does, that triggers an action, usually a call to a JavaScript function. Examples of events can be changing an input field, clicking on a button, or loading an HTML page.

Handling events in React is very similar to how you’d handle events with vanilla JS, with a few syntax differences. For example, here how you’d do it in HTML:

<button onclick=”callSomeFunction()”>
	Button that calls some function
</button>

In React, you’d write something like this:

<button onClick={callSomeFunction}>
	Button that calls some function
<button>

A good way of understanding event handling in React works is by writing a simple Toggle button that turns on and off. Here is the code snippet for a Toggle button implemented using a React class component.

class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isToggleOn: true};
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(state => ({
      isToggleOn: !state.isToggleOn
    }));
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        {this.state.isToggleOn ? 'ON' : 'OFF'}
      </button>
    );
  }
}

ReactDOM.render(
  <Toggle />,
  document.getElementById('root')
);

Before we move on to writing a functional component that does that same thing, let’s understand why we need to bind our event handler. Methods in JavaScript classes are not bound to their instance by default. What the bind() method does is, creates a new this.handleClick function that has its this keyword set to the provided value. Without this binding, handleClick’s this keyword wouldn’t know if the state is ON or OFF.