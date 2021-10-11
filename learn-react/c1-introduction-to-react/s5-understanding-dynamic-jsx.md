```javascript
const element = <h1>Hello, world!</h1>;
```

This funny tag syntax is neither a string nor HTML.

It is called JSX. It stands for JavaScript XML. JSX is a syntax extension to JavaScript.
When compiled, JSX produces plain JavaScript that creates React elements. We will explore
rendering them to the DOM in the next section. Below, you can find the basics of JSX
necessary to get you started.

You can use Babel to compile JSX to `React.createElement()` calls.

These two examples are identical:

```javascript
const element = (
    <h1 className="greeting">
        Hello, world!
    </h1>
);
```

```javascript
const element = React.createElement(
    'h1',
    {
        className: 'greeting'
    },
  'Hello, world!'
);
```

`React.createElement()` performs a few checks to help you write bug-free code but essentially it
creates an object like this:

```javascript
// Note: this structure is simplified
const element = {
    type: 'h1',
    props: {
        className: 'greeting',
        children: 'Hello, world!'
    }
};
```

These objects are called React elements. You can think of them as descriptions of what you want to
see on the screen. React reads these objects and uses them to construct the DOM and keep it up-to-date.

> React doesn’t require using JSX, but most people find it helpful as a visual aid when working
> with UI in JavaScript. It also allows React to show more useful error and warning messages.
> We recommend using it with React to describe what your UI should look like. JSX may remind
> you of a template language, but it comes with the full power of JavaScript.