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
