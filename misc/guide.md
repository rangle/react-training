---
layout: page
title: "Instructors' Guide"
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

<a id="a0-react-intro"></a>
### [Introduction to React]({{'/a0-react-intro/'|absolute_url}})

FIXME

<a id="a1-start"></a>
### [Getting Started]({{'/a1-start/'|absolute_url}})

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

<a id="a2-component"></a>
### [Making a Component]({{'/a2-component/'|absolute_url}})

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

<a id="a3-outline"></a>
### [Next Steps]({{'/a3-outline/'|absolute_url}})

- Demo the final app at the start of this section, making the URL available for trainees
- Demo without changing `index.js` to illustrate the error produced by missing props
- Make sure each `Card` has different values to illustrate how each card is different but the same
- Copy and paste individual cards before moving to list format
- Mention Flow/TypeScript as static analysis options

<a id="a4-cardlist"></a>
### [Creating a Card List]({{'/a4-cardlist/'|absolute_url}})

- Put some robot definitions in `robots.js` and import that rather than hard-coding into `CardList`
- Update `CardList` to accept the array as the `robots` prop (which is our array of objects)
- Don't add `key` prop to the generated `Card` elements at first to show a very common error
- Finish wiring up the pieces and then demo
- This is a good opportunity to do some simple exercises with `map` and `filter` (and possibly other higher-order functions)
  - Map: take an array of numbers and multiply them by 2
  - Filter: filter out odd numbers in an array of numbers
  - Reduce: sum up an array of numbers, multiply an array of numbers

<a id="/a5-container/"></a>
### [Creating the Container]({{'/a5-container/'|absolute_url}})

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

<a id="/a6-lifecycles/"></a>
### [Lifecycles]({{'/a6-lifecycles/'|absolute_url}})

- Summarize the three different categories of lifecycle methods
- Explain mounting and go into componentDidMount as a place to do AJAX requests
- Don't spend much time at this point on updating and unmounting
- Go back to `componentDidMount` and use that to transition into coding the AJAX call to get robots
- Create a robot provider
- Implement AJAX call in `App.js`'s `componentDidMount` member

<a id="/a7-react-summary/"></a>
### [React Summary]({{'/a7-react-summary/'|absolute_url}})

- Go over each of the main concepts of React: components, state, props and JSX. This is to show how simple React really is; and how it isn't that complicated.
- Go back and show how what has been done so far connects to what React is in essence:
  - Reactive since views are re-rendered on state updates
  - Declarative since renders are pure and can be expressed as a single JSX expression
  - The app is built from the composition of small components
-  To build interactivity, we combine callbacks (methods) with props, and state
-  It's best practice as apps get bigger, it solves a huge problem that massive projects have faced in the past. This is why people love React. React has these walls to guide you in this style of mentality. So when you build apps, you are using good practices.

<a id="/b0-redux-intro/"></a>
### [Introduction to Redux]({{'/b0-redux-intro/'|absolute_url}})

- Start by going over what problems Redux tries to address
  - State is getting more complicated
  - GUIs can interact with many different parts of the state
  - Web applications have client/server dynamic
- Summarize what Redux is
- Use diagram to explain the main abstractions in short detail and how all state updates must follow this pattern in order to achieve benefits of predictability
- Provide more context regarding the roles of Actions, Reducer and Store in more detail

<a id="/b1-install/"></a>
### [Installation]({{'/b1-install/'|absolute_url}})

- Install redux and react-redux into the robodex app
- Go to the Redux Devtools Extension readme to give trainees the option to download the version they need
- Go to Chrome Store, install and show how to confirm it's been installed correctly
- Show that no store has been detected yet

<a id="/b2-action-reducer/"></a>
### [Actions and Reducers]({{'/b2-action-reducer/'|absolute_url}})

- Create a reducers folder and create a robotSearchReducer
- Create an actions folder and create a `CHANGE_SEARCHTERM` action
- Update reducer to handle the action
- Add store using `createStore` in index.js, feeding the robotSearchReducer to it
- Use debugger to examine contents of store
- Use `Provider` from react-redux, assign the store to it and then wrap the App component
- Inspect using Redux DevTools to see if everything has completed alright

<a id="/b3-store/"></a>
### [Providing a Store]({{'/b3-store/'|absolute_url}})

FIXME

<a id="/b4-connect/"></a>
### [Making Connections]({{'/b4-connect/'|absolute_url}})

FIXME

<a id="/b5-logging/"></a>
### [Redux Logging]({{'/b5-logging/'|absolute_url}})

FIXME

<a id="/b6-thunk/"></a>
### [Redux Thunk]({{'/b6-thunk/'|absolute_url}})

FIXME

<a id="/b7-merge/"></a>
### [Merging]({{'/b7-merge/'|absolute_url}})

FIXME
