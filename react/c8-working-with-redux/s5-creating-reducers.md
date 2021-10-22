Reducer is a function that receives two parameters: the state and the action. Based on the action type, it understands how to appropriately change the state. It changes the state immutably and returns a new state.

When creating reducers there are three rules you must follow:

They should only calculate the new state value based on the state and action arguments
They are not allowed to modify the existing state. Instead, they must make immutable updates, by copying the existing state and making changes to the copied values.
They must not do any asynchronous logic, calculate random values, or cause other "side effects"

Here is an example of the counter reducer.

function counterReducer(state = initialState, action) {
 // Check to see if the reducer cares about this action
 if (action.type === 'counter/increment') {
   // If so, make a copy of `state`
   return {
     ...state,
     // and update the copy with the new value
     value: state.value + 1
   }
 }
 return state
}
