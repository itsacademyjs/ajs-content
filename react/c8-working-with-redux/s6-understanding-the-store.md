
The centralized state that we have been talking about lives in a place called “store”.

Stores can be created by passing in a reducer.

import { configureStore } from '@reduxjs/toolkit'
const store = configureStore({ reducer: counterReducer })

Stores have an in-built method called getState() which returns the current state of the store.

console.log(store.getState())