When a component in your hierarchy throws an error, the whole app crashes with cryptic errors. But when you have a modular hierarchy, other modules in your UI should continue to function regardless of other modules failing.

For example, let’s say you are developing an app like WhatsApp. In general, we can consider the camera tab, chats tab, status tab, and calls tab as four different modules. Now if there is an exception thrown in the calls tab, the user should still be able to access the remaining tabs.

To support this, React allows you to create error boundaries. When an exception is thrown within their subtree, an error boundary component catches the exception like the catch clause in try statements. The error is then logged and a fallback UI is rendered.
Usually, you would create a single error boundary component and reuse it throughout your project.

At the moment, you cannot create error boundaries with functional components. You need to override componentDidCatch(error, errorInfo) method and implement the static getDerivedStateFromProps(error) function in your class component.

componentDidCatch(error, errorInfo) is responsible for logging the error to the console. getDerivedStateFromProps(error) is responsible for updating the component state so in the next render the fallback UI can be rendered.

Error boundaries do not catch errors thrown by event handlers. Unlike render and lifecycle methods, event handlers are not invoked when rendering. Therefore, React still knows what to render when event handlers throw exceptions.

 
import React from "react";
 
export default class ErrorBoundary extends React.Component {
 
   constructor(props) {
       super(props);
 
       this.state = {
           hasError: false
       };
   }
 
   static getDerivedStateFromError(error) {
       return {
           hasError: true
       };
   }
 
   componentDidCatch(error, errorInfo) {
       console.log(error, errorInfo);
   }

   render() {
       if (this.state.hasError) {
           return (<div>Something went wrong!</div>);
       }
 
       return this.props.children;
   }
}

