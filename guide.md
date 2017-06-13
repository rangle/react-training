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

FIXME

### [Lifecycles](/a6-lifecycles/)

FIXME

### [Conclusion](/a7-conclusion/)

FIXME

## Part 2: Redux

FIXME

### [Introduction to Redux](/b0-redux-intro/)

FIXME

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
