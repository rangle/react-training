---
layout: page
permalink: /redux-intro/
---

---

## The State Problem

- Applications are becoming more complex
- GUI applications have many different points of interaction, leading to different sources of state updates
- Web applications have to reconcile state between client and server
- Asynchronous nature of JavaScript and server-side calls introduces additional points of failure
- Server side rendering, caching, and distributed data add more complexity

---

## What is Redux

<div align="center" markdown="1">
  <em>Redux is a predictable state container for JavaScript apps.</em>
</div>

- A framework for managing state
- Streamlines state interactions using a common pattern
- Removes two-way interaction in favor of a uni-directional data flow

---

## Three Principles

- A single source of truth
- State is read-only
- State is updated using pure functions

---

## How Redux Works

![Redux Flow]({{'img/redux-flow.png'|absolute_url}})

FIXME: replace [this diagram](http://www.mrscottmcallister.com/assets/img/redux-flow.png) with a Rangle version

---

## Actions

- The sole mechanism for inducing changes in state
- Application dispatches actions whenever an event happens
  - E.g., button clicked, page has finished loading, AJAX call has returned data
- Actions contain:
  - Something that identifies the change
  - Any additional information needed to update the state

---

## Reducer

- The method by which state is actually changed
- Takes the "before" state and the action and returns the "after" state
- Follows the same data flow as the general programming concept of a "reducer"

---

## Store

- Where the entire application state exists
- An application should only have one store
- In larger applications, the store will have several parts
  - Partitioning state is a key architectural decision

---

## Getting Redux

- Redux is available via NPM
  - `npm install redux`
- There is also a package that provides easy interoperability between Redux and React called `react-redux`
  - `npm install react-redux`
  - Makes integration easier but is not absolutely necessary

---

## Redux DevTools

- [Redux DevTools][redux-devtools] is a debugging tool that allows you to:
  - Visualize your application's current state
  - Move forward and backwards throughout your state (time travelling!)
- Available for Chrome, Firefox and Electron and other environments

[redux-devtools]: https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd
