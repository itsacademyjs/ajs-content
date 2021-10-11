Mutable" means "changeable". If something is "immutable", it can never be changed.

JavaScript objects and arrays are all mutable by default. If I create an object, I can change the contents of its fields. If I create an array, I can change the contents as well:

const obj = { a: 1, b: 2 }
// still the same object outside, but the contents have changed
obj.b = 3
 
const arr = ['a', 'b']
// In the same way, we can change the contents of this array
arr.push('c')
arr[1] = 'd'

In order to change an object immutably, you have to create a new array or object, spread the content of the previous array or object and change the key or index you want to make a change to.

You have already seen how to do this while updating object states in class components.

Redux expects that all states you store in the centralized Redux store must be updated immutably. Now let us talk about some terminology.


