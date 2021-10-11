Let's consider the following example:
```javascript
<h1>Hi! My name is Samuel Rowe!</h1>
```

In this example, we render a simple `h1` element saying "Hi! My name is Samuel Rowe!"
the name is hard coded.

How can we make the content of the element dynamic? What if the name was stored in a
variable? This is exactly why JSX allows you to embed JavaScript expressions.

In the example below, we declare a variable called name and then use it inside JSX by wrapping
it in curly braces:

```javascript
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

You can put any valid JavaScript expression inside the curly braces in JSX.
For example, `2 + 2`, `user.firstName`, or `formatName(user)` are all valid
JavaScript expressions.

In the example below, we embed the result of calling a JavaScript function,
`formatName(user)`, into an `h1` element.

```javascript
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

We split JSX over multiple lines for readability. While it isn't required, when doing this,
we also recommend wrapping it in parentheses to avoid the pitfalls of automatic semicolon
insertion.