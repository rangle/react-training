---
layout: page
permalink: /redux-logging/
---

---

## What is Redux Middleware?

- Similar to middleware in other libraries or frameworks
- Adds a way for 3rd parties to introduce their own logic or processing
- Runs between an action being dispatched and when it hits the reducer

---

## Logging Middleware

- Since all state updates happen through Redux actions, we have a centralized point to intercept and log state changes
- All actions having a serializable type gives us a human readable name to understand the intent of state changes
- Pure reducers make logging the before state and after state very useful and simple
