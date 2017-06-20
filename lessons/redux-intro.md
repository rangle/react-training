---
layout: lesson
permalink: /redux-intro/
---

---

## The State Problem

- Applications are progressively becoming more complex
- GUI based applications have many different points of interaction, leading to different sources of state updates
- Web applications have to reconcile state between client and server
- Asynchronous nature of JavaScript and server side calls introduces additional points of failure
- Server side rendering, caching and distributed data add more complexity

---

## What is Redux

Redux is a predictable state container for JavaScript apps.

- A framework for managing state
- Streamlines state interactions into a common pattern
- Removes two-way interaction in favor of a uni-directional data flow

---

## The 3 principles

- Single source of truth
- State is read only
- Changes are made using pure functions

---

## How Redux Works

TODO: Add rangle version of this diagram

http://www.mrscottmcallister.com/assets/img/redux-flow.png


---

## Actions

- The sole mechanism for inducing changes in state
- Dispatched whenever some event happens, eg. button clicked, page has finished loading, ajax call has returned data


---

## Reducer

- The method by which state is actually changed
- Takes the "before" state and returns the "after" state
- Follows the same data flow as the general programming concept of the "reducer"

---

## Store

- Where the entire application state exists
- An application should only have one store
- In larger applications, the store will be split into multiple slices

---

## Getting Redux

- Redux is available through npm: `npm install redux`
- There is also a package that provides easy interoperability between redux and react called _react-redux_. `npm install react-redux`
- react-redux makes integration easier but is not absolutely necessary

---

## Redux DevTools

- Redux DevTools is a debugging tool that allows you to:
  - visualize your application's current state
  - move forward and backwards throughout your state (time travelling!)
- Available for Chrome, Firefox and Electron and other environments
