---
layout: page
permalink: /guide/
---

<a id="general"></a>
## General

- Let the audience pick the high level topics and perhaps you don't need to cover some
  - You can give a brief overview of the topics and let the audience pick what they want
- Simple demo
- Intelligent interrupts
  - Structure into your talk, breaks for the audience to interact
  - Encourage a conversation about the topic
  - Permission to interact
  - Two sticky notes; one for passive help and one for active help
- Balanced chance to speak, sticky note to indicate if you've spoken already to prevent over contributor
- Bring paper, pens, and encourage doodling
- Quiz them
  - Mind maps: draw them while listening and compare at intervals
  - Compare mind map at the end to my mind map to encourage people to pay attention
- Build something that represents the thing you were talking about
  - I.e., building blocks to represent a pipeline of processes

<a id="react-intro"></a>
### [Introduction to React]({{"/react-intro/"|absolute_url}})

- Share requirements for getting setup:
  - Node/NVM
  - Editor
  - `create-react-app`
- Create a Robodex app using `create-react-app`
- Walk through created folder and have a look at some basic Node project stuff
  such as `package.json` and `node_modules`
- Describe what folders do what and show `README.md`
- Describe `create-react-app` commands before serving the app
- Serve the app and demo

<a id="react-component"></a>
### [Making a Component]({{"/react-component/"|absolute_url}})

- Explain what components are, including description for rendering and props
- Explain what JSX is
- Create a stateless greeting component and break each part down into detail
- Talk about ReactDOM
  - Does the actual work of inserting React components into the DOM tree
  - Allows other renderers for different platforms/uses
- Replace `App` in `index.js` with `Greet`
- Describe props being inputs from parent component
  - Allows composability and extensibility of components
- Add props to `Greet` component and change text to rely on props
- Pass in props from `index.js`
- Talk about destructuring props
- Explain how embedded expressions work
- Introduce Tachyons, explain what it is and how it changes styling approach
  - Contrast with semantic approach
- Start styling the greeting component
  - Open up docs to give the audience the opportunity to see it
- Explain the oddity with `className` and how attribute string binding works

<a id="react-outline"></a>
### [Next Steps]({{"/react-outline/"|absolute_url}})

- Demo the final app at the start of this section, making the URL available for trainees
- Demo without changing `index.js` to illustrate the error produced by missing props
- Make sure each `Card` has different values to illustrate how each card is different but the same
- Copy and paste individual cards before moving to list format
- Mention Flow/TypeScript as static analysis options

<a id="react-cardlist"></a>
### [Creating a Card List]({{"/react-cardlist/"|absolute_url}})

- Put some robot definitions in `robots.js` and import that rather than hard-coding into `CardList`
- Update `CardList` to accept the array as the `robots` prop (which is our array of objects)
- Don't add `key` prop to the generated `Card` elements at first to show a very common error
- Finish wiring up the pieces and then demo
- This is a good opportunity to do some simple exercises with `map` and `filter` (and possibly other higher-order functions)
  - Map: take an array of numbers and multiply them by 2
  - Filter: filter out odd numbers in an array of numbers
  - Reduce: sum up an array of numbers, multiply an array of numbers

<a id="/react-container/"></a>
### [Creating the Container]({{"/react-container/"|absolute_url}})

- Ask learners how to connect search box to parent component before doing work
- Show details of adding the event handler to `SearchBox` component's `onChange` event
- Implement `onSearchChange` in `App.js` as class member function
- Demo that change handler is being called using console log before adding filter logic
- Discuss how to handle search term within app -> as state in App component
- Go over how stateless components don't re-render even if inputs change
- Investigate render stage using `console.log` or debugger
- Compare `App.js` class syntax to stateless component
- Rewrite `App.js` as stateless component to highlight the similarities
- Go back to class syntax and add an empty `robots` array to state
- Add a delayed `setState` call using `setTimeout`
- Explain how `setState` is async and batches updates
  - Accepts second argument for sequencing calls after state has updated
- Point out the error calling `setState` due to how JavaScript resolves `this`
  - Then change `onSearchChange` to an arrow function
- Demo search functionality
- Note that it is not safe to keep a reference to the event given to the handler
  due to React's synthetic event system

**Side note: This is a good point for a break**

<a id="/react-lifecycles/"></a>
### [Lifecycles]({{"/react-lifecycles/"|absolute_url}})

- Summarize the three different categories of lifecycle methods
- Explain mounting and go into componentDidMount as a place to do AJAX requests
- Don't spend much time at this point on updating and unmounting
- Go back to `componentDidMount` and use that to transition into coding the AJAX call to get robots
- Create a robot provider
- Implement AJAX call in `App.js`'s `componentDidMount` member

<a id="/react-summary/"></a>
### [React Summary]({{"/react-summary/"|absolute_url}})

- Go over each of the main concepts of React: components, state, props and JSX. This is to show how simple React really is; and how it isn't that complicated.
- Go back and show how what has been done so far connects to what React is in essence:
  - Reactive since views are re-rendered on state updates
  - Declarative since renders are pure and can be expressed as a single JSX expression
  - The app is built from the composition of small components
-  To build interactivity, we combine callbacks (methods) with props, and state
-  It's best practice as apps get bigger, it solves a huge problem that massive projects have faced in the past. This is why people love React. React has these walls to guide you in this style of mentality. So when you build apps, you are using good practices.

<a id="/redux-intro/"></a>
### [Introduction to Redux]({{"/redux-intro/"|absolute_url}})

- Start by going over what problems Redux tries to address
  - State is getting more complicated
  - GUIs can interact with many different parts of the state
  - Web applications have client/server dynamic
- Summarize what Redux is
- Use diagram to explain the main abstractions in short detail and how all state updates must follow this pattern in order to achieve benefits of predictability
- Provide more context regarding the roles of Actions, Reducer and Store in more detail
- Install redux and react-redux into the robodex app
- Go to the [Redux Devtools Extension][redux-devtools] README to give trainees the option to download the version they need
- Go to Chrome Store, install and show how to confirm it's been installed correctly
- Show that no Redux store has been detected yet

<a id="/redux-action-reducer/"></a>
### [Actions and Reducers]({{"/redux-action-reducer/"|absolute_url}})

- Create a reducers folder and create a robotSearchReducer
- Create a constants file and export a changeSearchTerm action
- Create an actions folder and create a `CHANGE_SEARCHTERM` action creator
- Update reducer that:
  - handles the action
  - takes a default state, and returns the same state when no action constants are matched
- emphasize that reducers must be pure, and return a valid state in all cases

<a id="/redux-store/"></a>
### [Providing a Store]({{"/redux-store/"|absolute_url}})

- Add store using `createStore` in index.js, feeding the robotSearchReducer to it
- Use debugger to examine contents of store
- Use `Provider` from react-redux, assign the store to it and then wrap the App component
- Inspect using Redux DevTools to see if everything has completed alright

<a id="/redux-connect/"></a>
### [Making Connections]({{"/redux-connect/"|absolute_url}})

- Do a simple store.subscribe solution that calls `React.render` on the application
- Demo the app to see that Redux is working as expected
- This solution is more limited since it requires re-rendering the whole application for every state change
- Start with a basic connect solution provided by react-redux
- Import actions into app.js
- Create a mapStateToProps function that takes the state and returns an object with searchTerm
  - Explain how this function is a way of turning redux state into component props
- Create a mapDispatchToProps function that returns an `onSearchChange` prop that dispatches the changeSearchTerm action
  - Explain how this function is a way of mapping dispatcher functions to component props
- Import connect and connect the component to our mapping functions
- Change the default export to the connected App component
- This way of implementation makes it so that the component doesn't need to be aware of the implementation details of how it recieves context values, just that it gets them

<a id="/redux-logging/"></a>
### [Redux Logging]({{"/redux-logging/"|absolute_url}})

- Introduce the concept of Redux middleware
- It's similar to middleware in other libraries but it runs between the action and reducer
- Talk about logging middleware since it's probably the most obviously useful
- Install `redux-logger`
- Import and create the logger
- Apply the middleware and demo the logger to see that it logs to the console

<a id="/redux-thunk/"></a>
### [Redux Thunk]({{"/redux-thunk/"|absolute_url}})

- Introduce the concept of thunks as ways to delay evaluation and execution
- Show some quick examples with plain JS
- Talk about the benefits of why this is useful to redux, sometimes state updates need to be delayed
- Add new action constants for pending, success, and error
- Import the constants you just created in the actions file
  - Add an action creator for fetching robot data
    - Returns a function that accepts dispatch (and optionally getState since thunk provides it)
      - Inside the function...
      - Dispatch pending
      - Call fetch
      - On then fire the success action with payload
      - On error fire the error action
- Import the constants for the new action in the reducers file
    - Create a new reducer for robots data
        - Create a new initial state for robot data, is pending, and has error
        - Create a reducer function that will implement the new constants
    - Change the export default to export and add an export for the new reducer
- Change the import statement within index for the reducer to use curly braces to import each of the reducers separately
- Implement reducers through combineReducers before calling createStore
  - Explain that this can be done as a default export too (in reducers.js)
  - Import reduxThunk from redux-thunk and apply it as middleware
- Open App.js and import the new action
- Update mapStateToProps and mapDispatchToProps
  - Note, now that we're using combineReducers, you'll need to update the state.searchTerm to include reducer name (i.e. state.robotSearch.searchTerm)
- Replace the contents of componentDidMount to call the action to fetch robots

<a id="/redux-merge/"></a>
### [Merging]({{"/redux-merge/"|absolute_url}})

- Notify that mergeProps is one way to intercept props passed into a component and use that when interacting with state
- How we'll use it in this case is to help us with filtering robots
- Create a new function called mergeProps in App.js that takes state and dispatch arguments
- Add a new filteredRobots prop that filters the list of robots based on the search term
- Update the connect call to include mergeProps as the third param
- Use the filteredRobots prop in the CardList component to render the Cards

[redux-devtools]: https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd
