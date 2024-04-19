the Redux store is the single source of truth when it comes to application state. This also means that any time any
piece of your app wants to update state, it must do so through the Redux store. The unidirectional data flow makes it
easier to track state management in your app.

Here is an example that creates a redux store with a value of 5 for the state
(this is wrong there should be configureStore not createStore.)
```js
const reducer = (state = 5) => {
  return state;
}

// Redux methods are available from a Redux object
// For example: Redux.createStore()
// The store is defined here:
const store = Redux.createStore(reducer)
```
