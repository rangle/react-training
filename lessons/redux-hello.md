---
layout: page
permalink: /redux-hello/
---

---

## Start With Something Simple

- Build a single-page example that increments and decrements a counter
- Has all of the key elements of a real React/Redux application
- Load libraries from the web to keep things simple

---

## Page Outline

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <script src="https://fb.me/react-15.1.0.js"></script>
    <script src="https://fb.me/react-dom-15.1.0.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/redux/3.5.2/redux.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
    <title>Simplified Example</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
    ...all JavaScript will go here...
    </script>
  </body>
</html>
```

- Using Babel to translate JSX and ES6 into whatever the browser needs

---

## State

```js
const INITIAL_STATE = 0
```

- Doesn't get much simpler than that

---

## Actions

```js
const INCREASE = 'INCREASE'
const DECREASE = 'DECREASE'

function increase() {
  return { type: INCREASE }
}

function decrease() {
  return { type: DECREASE }
}
```

- Symbolic names instead of raw strings

---

## Reducer

```js
function counterReducer(state = INITIAL_STATE, action = {}) {
  switch (action.type) {
    case INCREASE:
      return state + 1

    case DECREASE:
      return state - 1

    default:
      return state
  }
}
```

- State will be initialized on the first call by default value of `state`
- Return a new state depending on the action type
  - If no action provided, `action.type` is `undefined`

---

## Connect to Redux

```js
let { createStore, combineReducers } = Redux

const rootReducer = combineReducers({ counter: counterReducer })
const store = createStore(rootReducer)
```

- `combineReducers` lets us build reducers separately for different parts of the application
  - Our application's actual state is an object with `counter` as its only key
- `createStore` then creates a store that passes actions through reducers

---

## Handling Changes

```js
store.subscribe(() => {
  ReactDOM.render(
    <div>
    
      <pre>
        { JSON.stringify(store.getState(), null, 2) }
      </pre>
      
      <button 
        onClick={ () => store.dispatch(increase()) }>
        Increase
      </button>
                
      <button 
        onClick={ () => store.dispatch(decrease()) }>
        Decrease
      </button>
    
  </div>,
    document.getElementById('root')
  )
})
```

- The store is an observable
- Every time state changes, it calls our (anonymous) callback...
- ...which does a React render
- Display the entire state using `JSON.stringify` with 2-level indentation
- Buttons that dispatch actions
  - `store.dispatch` means "handle this action"
  - Actions themselves are created by our utility functions

---

## Start Things Off

```js
store.dispatch({ type: 'INIT' })
```

- A pre-defined action that triggers the initial rendering

---

## Patterns

- Some of these steps are the same for every Redux application
- We will introduce tools that automate them
