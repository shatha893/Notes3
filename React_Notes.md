# React  

## React Hooks  

* They don't seem as bad as I thought it was.  

* useReducer()  
    * Helps with state management.
    * Sometimes we have complex states.
    * It's a replacement to `useState()`.
    * useReducer requires more setup.  
    * If you update a state that depends on another state it's best to use useReducer(). 
    * The syntax is as follows  
    `const [state, dispatchFn] = useReducer(reducerFn, initialState, initFn);`
      * First the state snapshot used in the component re-render/re-evaluation cycle.
      * Then A function that can be used to dispatch a new action (i.e. trigger an update of the state).
      * Then a function that is triggered automatically once an action is dispatched (via dispatchFn()) - it receives the latest state snapshot and should return the new, updated state.
      * Then the initial state.
      * A function to set the initial state programmatically.

