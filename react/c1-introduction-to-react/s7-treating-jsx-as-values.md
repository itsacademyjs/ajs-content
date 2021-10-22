After compilation, JSX expressions become regular JavaScript function calls and evaluate to
JavaScript objects.

This means that you can treat JSX like any other values in JavaScript! You can use it inside of
if statements, for loops, assign it to variables, accept it as arguments, and return it from functions.

```javascript
function renderGreeting(user) {
    let result = <h1>Hello, stranger.</h1>;
    if (user) {
      return <h1>Hello, {formatName(user)}!</h1>;
    }
    return result;
}
```

The above code snippet is equivalent to the following:

```javascript
function renderGreeting(user) {
  let result = React.createElement("h1", null, "Hello, stranger.");

  if (user) {
    return React.createElement("h1", null, "Hello, ", formatName(user), "!");
  }

  return result;
}
```