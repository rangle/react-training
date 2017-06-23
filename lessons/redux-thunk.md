---
layout: page
permalink: /redux-thunk/
---

---

## What Are Thunks?

- Thunks are functions that serve to delay execution of some code
- Useful for moving logic around to be executed asynchronously

---

## Why is this useful for Redux?

- Sometimes dispatching an action needs to happen somewhere down the line rather than immediately as a reaction to an event
- Ajax requests to APIs don't update state in response to an event, they update state in a response to data returned by API call

---

## Redux Thunk

- Provided as Redux middleware
- Allows for action creators to return not just an action, but a function that accepts dispatch
- Within the function, dispatch can then be called whenever the user likes
