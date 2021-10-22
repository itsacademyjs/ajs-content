The useEffect hook allows you to implement side effects such as fetching data from the backend, subscribing to events, and so on. You can use it as a replacement for componentDidMount, componentDidUpdate, and componentWillUnmount lifecycle methods.

You can simulate componentDidMount+componentDidUpdate, using the useEffect hook. The callback specified to the hook is called on every re-render if you do not specify a dependency list.


import React, { useState, useEffect } from 'react';
 
function Counter() {
 const [count, setCount] = useState(0);
 
 // This is equivalent to componentDidMount and componentDidUpdate
 useEffect(() => {
   document.title = `You clicked ${count} times`;
 });
 
 function updateCount() {
     setCount(count + 1);
 }
 
 return (
   <div>
     <p>You clicked {count} times</p>
     <button onClick={updateCount}>
       Click me
     </button>
   </div>
 );
}
 
export default Counter;


To simulate componentWillUnmount, you need to return a function to useEffect. Unlike class components, clean up happens on every re-render.

import React, { useState, useEffect } from "react";
 
function Counter() {
 const [seconds, setSeconds] = useState(0);
 
 function updateSeconds() {
   setSeconds(seconds + 1);
 }
 
 useEffect(function () {
   const reference = setInterval(updateSeconds, 1000);
 
   return function () {
     clearInterval(reference);
   };
 }, []);
 
 return (
   <div>
     <p
       style={{
         display: "flex",
         justifyContent: "center",
         alignItems: "center",
         height: "100vh",
       }}
     >
       {seconds}
     </p>
   </div>
 );
}
 
export default Counter;
 

 
Applying an effect and cleaning up on every re-render could affect performance significantly. To overcome this, you can pass a dependency list to useEffect.

import React, { useState, useEffect } from 'react';
 
function Counter() {
 const [count, setCount] = useState(0);
 
 // This is equivalent to componentDidMount and componentDidUpdate
 useEffect(() => {
   document.title = `You clicked ${count} times`;
 }, [ count, document ]);
 
 function updateCount() {
     setCount(count + 1);
 }
 
 return (
   <div>
     <p>You clicked {count} times</p>
     <button onClick={updateCount}>
       Click me
     </button>
   </div>
 );
}
 
export default Counter;
