---
layout: lesson
title: "Introduction to React"
permalink: /a0-react-intro/
---

---
## What is React?

- A Javascript UI framework based on declarative views
- Generate page with nested function calls that take data as input and produce HTML as output

---
## What Problems Does It Solve?

- Older UI frameworks built DOM trees imperatively
  - HTML initially be created on the server
  - Data stored on the HTML elements as attributes
- A lot of re-rendering (performance penalty)
- Tied tightly to browsers (in a world with a growing variety of devices)

---
## Core Architectural Principles

- DOM nodes are no longer a source of data
- Declarative view rendering and composition removes the need to understand DOM state when updating views
- View implementation details are easier to modularize
- It's faster: React only re-renders those parts of the view that need to be updated
