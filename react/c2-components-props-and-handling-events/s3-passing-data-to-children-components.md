You can pass properties to your components so that they can render based on the
properties you send them. These properties are called props.

Here is an example of passing the `name` prop to the `Header` component:

```javascript
import { Component } from "react";

class Header extends Component {
    render() {
        return (<h1>Hello, {this.props.name}</h1>);
    }
}

export default Header;
```

Here’s another example:

```javascript
import "./App.css";

const Formula = (props) => {
  const result = props.length + props.breadth;

  return (
    <div className="result-container">
      <h1 className="result-heading">{result}</h1>
    </div>
  );
};

const Container = () => {
  return <Formula length={100} breadth={50} />;
};

export default Container;
```

You may use quotes to specify string literals as props:

```javascript
const element = <div tabIndex="0"></div>;
```

You can use curly braces to embed a JavaScript expression in a prop:

```javascript
const element = <img src={user.avatarUrl}></img>;
```

Don’t put quotes around curly braces when embedding a JavaScript expression in
a prop. You should either use quotes (for string values) or curly braces
(for expressions), but not both in the same prop.

Since JSX is closer to JavaScript than to HTML, React DOM uses camelCase property naming convention instead of HTML attribute names.

For example, onclick becomes onClick in JSX, and tabindex becomes tabIndex.

The `class` attribute becomes `className`.

If a tag is empty, you may close it immediately with />, like XML:
```javascript
const element = <img src={user.avatarUrl} />;
```
