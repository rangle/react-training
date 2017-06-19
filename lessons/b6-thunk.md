---
layout: lesson
title: "Redux Thunk"
permalink: /b6-thunk/
---

-   Run and discuss; walk through the code to review all the steps

-   Now let's do it again, this time with robot data being fetched from json

-   Start off by installing thunk and explaining what it provides
    -   npm install --save redux-thunk
    -   It's middleware that provides getState and dispatch to functions that are passed to dispatch; useful for side effects, like ajax calls
-   We're going to create a new action for fetching the robot data asynchronously
    -   Open the constants.js file
        -   add a new action types for pending, success, and error
    -   Open the actions.js file
        -   Import the constants you just created
        -   Add an action creator for fetching robot data
            -   Returns a function that accepts dispatch (and optionally getState since thunk provides it)
                -   Inside the function…
                -   Dispatch pending
                -   Call fetch
                -   On then fire the success action with payload
                -   On error fire the error action
    -   Open the reducers.js file
        -   Import the constants for the new action
        -   Create a new reducer for robots data
            -   Create a new initial state for robot data, is pending, and has error
            -   Create a reducer function that will implement the new constants
        -   Change the export default to export and add an export for the new reducer

-   Open index.js
    -   change the import statement for the reducer to use curly braces to import each of the reducers separately
    -   It might be a good idea to explain why using multiple files is better than multiple reducers in one file
    -   Illustrate combineReducers before calling createStore
        -   Add the import for combineReducers from redux
        -   Const rootReducer = combineReducers({ reducer1, reducer2 })
        -   Update createStore to use rootReducer
        -   Explain that this can be done as a default export too (in reducers.js)
    -   Import applyMiddleware from redux
    -   Import reduxThunk from redux-thunk
    -   Update createStore to pass a second param: applyMiddleware(reduxThunk)

-   Open App.js and import the new action

-   Update mapStateToProps and mapDispatchToProps
    -   Note, now that we're using combineReducers, you'll need to update the state.searchTerm to include reducer name (i.e. state.robotSearch.searchTerm)

-   Update propTypes

-   Remove the constructor

-   Replace the contents of componentDidMount to call the action to fetch robots

*Optional*

Update the code to show how you can do the same without thunk

-   Update the requestRobots action in actions.js

```
const requestRobots = (dispatch) => { dispatch (pending), fetch.then(dispatch(success)).catch(dispatch(error))
```

-   Open index.js and remove applyMiddleware and reduxThunk

-   Open app.js and change mapDispatchToProps()
    -   requestRobots: () => requestRobots(dispatch)

TODO if there is enough time

-   Implement another container to illustrate another redux aware component

-   Pass data between the containers

-   Split reducers into individual files into reducers folder

-   How to know when to create additional containers

-   Components are only for presentation; not for data proxy, thus redux instead of a container for just holding state
