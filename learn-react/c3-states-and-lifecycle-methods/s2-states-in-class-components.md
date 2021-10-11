In React class components, using states is easy. You just initialize the this.state object in your constructor, like this -

import React from 'react';
 
class Clock extends React.Component {
  constructor(props) {
    super(props);
 
   this.state = {date: new Date()};
 }
 
   {
   /* You can write your render method here */
   }
}

