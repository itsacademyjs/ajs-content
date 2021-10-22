There is only one way the store can be changed, by calling the dispatch function. This dispatch function accepts an action object as a parameter.

Usually, the action object is not directly passed as parameter to the dispatch function, but instead, a function that returns an action object is called while a dispatch function is called as shown below:




const increment = () => {
 return {
   type: 'counter/increment'
 }
}
 
store.dispatch(increment())
 
console.log(store.getState())
// {value: 2}
