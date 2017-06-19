---
layout: lesson
title: "Actions and Reducers"
permalink: /b2-action-reducer/
---

-   Create the action, actiontype constant, and reducer
    -   Create src/actions.js file (touch src/actions.js)
    -   Create src/constants.js file (touch src/constants.js)
    -   Edit the actions.js file
    -   Add action creator for setSearchTerm (text => dispatch(...))

```
export const setSearchTerm = (term) =>
({ type: ‘SET_SEARCH_TERM': payload: term })
```

-   Use a hard-coded string at first for type, but then explain why it's better to use a constant

-   Edit the constants file to export a new constant for the action type

```
export const SET_SEARCH_TERM = ‘SET_SEARCH_TERM';
```

-   Go back to the actions file
    -   Import the constant
    -   Replace the hard-coded type with the constant

-   Create a src/reducers.js file (touch src/reducers.js)

-   Edit the reducers.js file
    -   Create an initial state object that cannot be mutated (i.e. use const)
    -   Import the action type from constants
    -   Create function for the reducer
        -   Default state to initial state
        -   Default action to empty object (to prevent undefined error when accessing action.type in switch)
        -   Create a switch statement
            -   with a case for the action type
            -   Default statement for returning state
            -   Object.assign({}, state, {searchTerm: action.payload})
                === pure functions. You always return a new state in a reducer.
            -   Explain that you could use an if instead of a switch
            -   Explain that this function must be pure and return a valid state each time
