Your JSX expressions always need to have a single root component. Let’s say you have a function that returns two adjacent components. You cannot return multiple components without wrapping them with a component. But what if you do not wish to wrap them with a DOM component? That’s where you would use fragments.

Long form syntax:
<React.Fragment>
  <A />
  <B />
</React.Fragment>

Short form syntax:
<>
  <A />
  <B />
</>

When you are rendering a list of fragments you will need to pass the key prop like any other component. You cannot use props with the short form syntax.
