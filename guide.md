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

FIXME

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
