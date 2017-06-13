---
layout: lesson
title: "Instructors' Guide"
permalink: /guide/
---

## General

-   Let the audience pick the high level topics and perhaps you don't need to cover some
    -   You can give a brief overview of the topics and let the audience pick what they want

-   Simple demo

-   Trivia/Crossword puzzle, statements with a blank that they can fill in the blank

-   Intelligent Interrupts
    -   Structure into your talk, breaks for the audience to interact
    -   Encourage a conversation about the topic
    -   Permission to interact
    -   Two sticky notes; one for passive help and one for active help

-   Balanced chance to speak, sticky note to indicate if you've spoken already to prevent over contributor

-   Bring paper, pens, and encourage doodling

-   Quiz them
    -   Mind maps; draw them while listening and compare at intervals
        -   Compare mind map at the end to my mind map; this encourages people to pay attention

-   Build something that represents the thing you were talking about
    -   I.e. building blocks to represent a pipeline of processes

## Part 1: React

FIXME

### [Introduction to React](/a0-react-intro/)

FIXME

### [Getting Started](/a1-start/)

- Share requirements for getting setup:
    - Node/NVM
    - Editor ie. VS Code
    - create-react-app
- Create a Robodex App using create-react-app
- Walk through created folder and have a look at some basic Node project stuff such as package.json, node_modules. Describe what folders do what and show README.md
- Describe create-react-app commands before serving the app
- Serve the app and demo

### [Making a Component](/a2-component/)

- Explain what components are, including description for rendering and props
- Explain what JSX is
- Create a stateless greeting component and break each part down into detail
- Talk about ReactDOM
    - does the actual work of inserting React components into the DOM tree
    - allows other renderers for different platforms/uses
- Replace `App` in _index.js_ with `Greet`
- Describe props being inputs from parent component. Allows composability and extensibility of components
- Add props to Greet component and change text to rely on props
- Pass in props from _index.js_
- Talk about destructuring props
- Explain how embedded expressions work
- Introduce Tachyons and explain what it is and how it changes styling approach, contrast with semantic approach
- Start styling the greeting component, open up docs to give the audience the opportunity to see it
- Explain the oddity with className and how attribute string binding works

### [Outline of Future Work](/a3-outline/)


We can now delete the HelloComponent and start building the app with the Card component. We are going to make a Robodex.

-   TODO: demo the final app, make url available for trainees

-   Create the Card.js as a stateless component with hardcoded mock data initially
```
<div>
    <img alt='photo'
         src='[*//robohash.org/test*](https://robohash.org/test)?size=200x200'/>
    <div>
        <h2>Jane Doe</h2>
        <p>jane.doe@gmail.com</p>
    </div>
</div>
```

-   Convert the hard-coded values into id, name, email props
-   Now we're going to add json data to make each card different. `robots.js` is available from the lesson 3 folder in the repo
- Show destructuring of props passed in
- Introduce propTypes as an option for validating passed in props

- Install `prop-types` package and implementing something like the following
```
Card.propTypes = {
    id: React.PropTypes.number.isRequired,
    name: React.PropTypes.string.isRequired,
    email: React.PropTypes.string.isRequired
};
```

- Add the below classes to the Card component
```
<div className='bg-light-green dib br3 pa3 ma2 grow'>
    <img role='presentation'
         src={`//robohash.org/${id}?size=200x200`} />
    <div>
        <h2>{name}</h2>
        <p>{email}</p>
    </div>
</div>
```

- Demo without changing index.js to illustrate the error you get when missing props
- Make sure each Card has different values to illustrate how each card is different but the same
- Copy and paste individual cards before moving to list format
- Mention Flow/TypeScript as static analysis options

### [Creating a Card List](/a4-cardlist/)

- This is a good opportunity to do some simple exercises with map, filter, reduce and possibly higher order functions. Some simple examples:
    - Map: take an array of numbers and multiply them by 2. Higher order function that returns a function that multiplies by argument passed to it
    - Filter: filter out odd numbers in an array of numbers
    - Reduce: sum up an array of numbers, multiply an array of numbers.

- Copying and pasting Cards is tedious and doesn't scale out for large numbers of cards, so we create a CardList component
- We'll create this using the markup in index.js as a hard-coded first step
- Create an array of objects in the function that will hold the static data
    - Then map over the array to generate the cards in the return JSX
    - Don't add `key` prop at first to show a very common error
    - Then you'll see it's best to put it into a variable and inject the variable into the return JSX
    - Then "wouldn't it be nice if we could pass this data into the component?"

- Update the component to accept the array as the `robots` prop (which is our array of objects)
- Finish wiring up the pieces and then demo

### [Creating the Container](/a5-container/)

- Go over how stateless components don't re-render even if inputs change
- Investigate render stage using console.log or debugger
- Compare App.js class syntax to stateless component
- Rewrite App.js as stateless component to highlight the similarities
- Go back to class syntax and add an empty `robots` array to state
- add a delayed `setState` call using `setTimeout`
- explain how `setState` is async and batches updates, accepts 2nd argument for sequencing calls after state has updated

- Create a SearchBox component, with the goal of listing only robots that match the search query
- Note that since key inputs are being handled by SearchBox component and robots are being provided by parent component, we need to have some method of integrating the two. Field answers from audience on what the solution should be
- Answer is to use App/parent as common 3rd party
- Show details of adding the event handler to SearchBox component's `onChange` event
- Implement `onSearchChange` in App.js as class member function
- Pass `onSearchChange` as a prop to the search box
- Demo that change handler is being called using console log before adding filter logic
- Discuss how to handle search term within app -> as state in App component
- Create a `searchTerm` state property on App component and have `onSearchChange` call `setState`
- Filter robots passed in render call using the search term
- Notice that this is an error with calling `setState`, this is due to how JavaScript resolves `this`
- Change `onSearchChange` to an arrow function
- Demo search functionality
- Note that it is not safe to keep a reference to the event given to the handler due to React's SyntheticEvent system

Side note: This is a good point for a break


### [Lifecycles](/a6-lifecycles/)

- Introduce lifecycles as phases that are generally useful for adding special procesing logic
- In some cases that logic replaces existing default logic
- Summarize the three different categories of lifecycle methods
- Explain mounting and go into componentDidMount as a place to do ajax requests.
- Discuss in short detail updating and unmounting
- Go back to componentDidMount and use that to transition into coding the ajax call to get robots
- Create a robot provider
- Implement ajax call in App.js `componentDidMount` member

### [Conclusion](/a7-conclusion/)

- Go over each of the main concepts of React: components, state, props and JSX. This is to show how simple React really is; and how it isn't that complicated.
- Go back and show how what has been done so far connects to what React is in essence:
    - Reactive since views are re-rendered on state updates
    - Declarative since renders are pure and can be expressed as a single JSX expression
    - The app is built from the composition of small components
-  To build interactivity, we combine callbacks (methods) with props, and state
-  It's best practice as apps get bigger, it solves a huge problem that massive projects have faced in the past. This is why people love React. React has these walls to guide you in this style of mentality. So when you build apps, you are using good practices.

## Part 2: Redux

FIXME

### [Introduction to Redux](/b0-redux-intro/)

- Start by going over what problems Redux tries to address
    - State is getting more complicated
    - GUIs can interact with many different parts of the state
    - Web applications have client/server dynamic
- Summarize what Redux is
- Use diagram to explain the main abstractions in short detail and how all state updates must follow this pattern in order to achieve benefits of predictability
- Provide more context regarding the roles of Actions, Reducer and Store in more detail

### [Installation](/b1-install/)

FIXME

### [Actions and Reducers](/b2-action-reducer/)

FIXME

### [Providing a Store](/b3-store/)

FIXME

### [Making Connections](/b4-connect/)

FIXME

### [Redux Logging](/b5-logging/)

FIXME

### [Redux Thunk](/b6-thunk/)

FIXME

### [Merging](/b7-merge/)

FIXME
