React has a powerful composition model, and it is not recommended to use Inheritance. Let’s first under what inheritance and composition are. Some components, like a Sidebar or a ListContainer, render a list of items or components. These components can be passed to them as props. Imagine you have a `<Library />` component, you can pass down many `<Book />` components to it. So we render the `<Library />` component which in turn renders its many children components.

But sometimes, we think about individual components as specialized versions of the containing component. For example, a `<SpecialBook />` is a specialized version of a `<Book />`.

Composition is rendering specific components but configuring existing generic components, and it is recommended to be used instead of Inheritance in React. Here is an example of composition in React, where a specialized component like WelcomeDialog is rendered by configuring a more generic Dialog component:

```javascript
function Dialog(props) {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">
        {props.title}
      </h1>
      <p className="Dialog-message">
        {props.message}
      </p>
    </FancyBorder>
  );
}

function WelcomeDialog() {
  return (
    <Dialog
      title="Welcome"
      message="Thank you for visiting our spacecraft!" />
  );
}
```