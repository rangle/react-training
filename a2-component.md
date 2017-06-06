---
layout: lesson
title: "Making a Component"
permalink: /a2-component/
---

# Components

---

## What are Components?

- The core building block of React applications
- Views that represent some chunk of the element tree
- Generate elements during a process known as __rendering__
- Can take inputs from parent components. Values that come from potential inputs are called __props__

---

## JSX

- Brings XML based language into JavaScript
- Can be created anywhere a JS object can be
- Non-standard JS, is converted into `React.createElement` calls during the build step

---

## Creating a Component

- Create a basic hello world component

```js
const Greet = () => <div>Hello world!</div>;

export default Greet;
```

- It's just a function
- What the function returns is what gets rendered
- Default export for components is a React convention

---

## ReactDOM

- Provides a way for elements created by React to be injected into the DOM
- Implementing React -> DOM rendering path decouples React elements from the underlying platform, can target platforms other than the DOM
- `render` inserts the rendered component to the matched element

---

## Props

- Props are inputs passed into a component from a parent component
- Used to dynamically change what a component renders or how it behaves

---

## Props, Destructuring and JSX

```js
export const Greet = (props) => <div>Hello {props.company}</div>;
```

becomes

```js
export const Greet = ({ company }) => <div>Hello {company}</div>;
```

- We can use destructuring assignment to get specific fields of props
- Use `{}` whenever we need to embed an expression within JSX blocks
- Embedded expressions are escaped
- Any JavaScript expression works, even function calls. Be careful not to call functions with side-effects.

---

## Styling With Tachyons

Tachyons is a css toolkit that is:

- __Atomic__:
    - Style rules are small and serve one purpose
    - Meant to be combined
    - Rule names infer implementation details rather than the semantics of the elements being styled
- __Class driven__: style rules are applied using classes
- __Responsive__: all style rules are built with support for responsive design
