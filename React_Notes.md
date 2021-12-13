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

## React Context  

* What is the point of it?  
It provides data to components no matter how deep they are in the components tree. The context is used to manage global data, e.g.global state, theme, services, user settings and more.  

* Using the context in React requires 3 simple steps:  
  1. Creating the context  
   The built-in factory function `createContext(default)` creates a context instance. We can use it as follows:  
      ```javascript
      import { createContext } from 'react';
      const Context = createContext('Default Value');
      ```  
    

  2. Providing the context  
   We can change the value of context and provide through the `value` prop  
      ```javascript
      function Main() {
     const value = 'My Context Value';
     return (
       <Context.Provider value={value}>
         <MyComponent />
       </Context.Provider>
     );} 
     ```  

  3. Consuming the context  
   We can consume the context through 2 ways  
   a) To use `useContext(Context)` React Hook  
      ```javascript
      import { useContext } from 'react';

      function MyComponent() {
        const value = useContext(Context);
        return <span> {value} </span>;
      }
      ```  
      The hook returns the value of the context `value = useContext(Context)`. The hook also makes sure to re-render the component when the context value changes.  

   b) Using a render function supplied as a child to `Context.Consumer` special component available on the context instance


   * If the context value changes then `<Context.Consumer>` will re-render its render function.

   * I wish I knew about this before. it would've saved me ALOT!  

  ## Dynamic Context  


  ## useEffect() 

  * It's for side effects which are the functional components that make calculations that don't target the output value and these calculations are named side-effects.
  * Side effects can be the fetching process, setTimeOut(), and more.
  * The syntax is `useEffect(callback[, dependencies]);`.

  * Dependencies let you control when the side-effect runs  
    * Not Provided: the side effect runs after every rendering   
      ```javascript
      import { useEffect } from 'react';
      function MyComponent() {
      useEffect(() => {
      // Runs after EVERY rendering
      });  
      }
      ```   

    * And empty array `[]`: the side-effect runs once after the initial rendering   
      ```javascript
      import { useEffect } from 'react';
      function MyComponent() {
      useEffect(() => {
      // Runs ONCE after initial rendering
      }, []);
      }
      ```  

    * Has props or state values `[prop1, prop2, ..., state1, state2]`: the side effect runs only when any dependency value changes  

      ```javascript
      import { useEffect, useState } from 'react';
      function MyComponent({ prop }) {
        const [state, setState] = useState('');
        useEffect(() => {
          // Runs ONCE after initial rendering
          // and after every rendering ONLY IF `prop` or `state` changes
        }, [prop, state]);
      }
      ```  

    * Component lifecycle with useEffect()

    