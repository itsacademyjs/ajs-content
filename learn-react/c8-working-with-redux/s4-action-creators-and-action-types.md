An action is a plain JavaScript object that has a type field. You can think of an action as an event that describes something that happened in the application.

An action object can have other fields with additional information about what happened. By convention, we put that information in a field called payload.

A typical action object might look like this:

const addTodoAction = {
 type: 'todos/todoAdded',
 payload: 'Buy milk'
}


Action creators are functions that return these action objects mentioned above. Action creators would look something like this: 

const addTodo = text => {
 return {
   type: 'todos/todoAdded',
   payload: text
 }
}
