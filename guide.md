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

FIXME

### [Making a Component](/a2-component/)

FIXME

### [Outline of Future Work](/a3-outline/)

FIXME

### [Creating a Card List](/a4-cardlist/)

FIXME

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
