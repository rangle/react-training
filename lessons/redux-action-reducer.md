---
layout: page
permalink: /redux-action-reducer/
---

---

## Adding Search

- Filter robots by matching their names against a search string
- Need to separate:
  - The entire list of robots
  - The currently-displayed list of robots
- Latter changes each time a search is run
  - Which means that search updates state
- We need:
  - An action object
  - With an action type
  - And a reducer to handle it

---

## Giving the Action a Name

- Define a constant to identify this action
  - Could use a raw string in this case
  - But we know we're going to want symbolic constants in namespaces eventually
- Put it in the file `constants.js`

```js
export const SET_SEARCH_TERM = "SET_SEARCH_TERM";
```

---

## Create an Action Object

- Define a function in `actions.js` to create an object representing an action
- Again, more elaborate than we need for this small example
- But we will eventually want to insulate ourselves from details
- Put this in `actions.js`
  - Larger applications will have one file of actions per module

```js
import CHANGE_SEARCHTERM from 'constants'

export const setSearchTerm = (text) =>  { type: CHANGE_SEARCHTERM, payload: text }
```

---

## Handle the Action

- Create the complement to our action generator in `reducers.js`
- A constant defining the initial state...
- ...that is the default value of reducer function's `state` argument...
- ...and an `action` that tells the function how to update state

```js
import { CHANGE_SEARCHTERM } from 'actions'

const initialState = {
  searchTerm: ''
}

const robotsSearch = (state=initialState, action={}) => {
  switch (action.type) {
    case CHANGE_SEARCHTERM:
      return Object.assign({}, state, {searchTerm: action.payload})
    default:
      return state
  }
}

export default robotsSearch;
```

- If our reducer doesn't recognize the action, it does nothing
  - Which makes it safe for us to chain reducers together
  - Note that `action` has a default value of `{}`
    - So `action.type` will be `undefined` if we forget to pass an action
- Use `Object.assign` to merge current state with action's payload
  - Does the right thing the first time because `initialState` is the default value of `state`
- Reducer functions *always* return a new state object
  - May recycle parts of the old state (we'll see that later)
  - But *never* mutate state in place
