---
layout: lesson
title: "Making a Component"
permalink: /react-component/
---

---
## What Are Components?

- The core building blocks of React applications
- Views that represent some chunk of the element tree
- Generate elements during *rendering*
- Can take inputs from parent components
  - Values passed in from the outside are called *props* (short for "properties")

---
## JSX

- Allows HTML-style tags to be freely mixed with JavaScript
- Can be created anywhere a JavaScript object can be
- *Not part of JavaScript*
  - JSX is onverted into calls to `React.createElement` during the build step

---
## Creating a Component

- Create a basic "hello world" component

```js
const Greet = () => <div>Hello world!</div>;

export default Greet;
```

- `Greet` is just a function returning text
  - JSX-to-JavaScript compilation wraps the return in quotes
  - Transformation is more complicated in bigger examples, but the idea is the same
- Using a default export for components is a React convention
  - `Greet.js` will (almost always) export `Greet` and only `Greet`

---
## ReactDOM

- Provides a way for elements created by React to be injected into the DOM
- Implementing a React-to-DOM rendering path decouples React elements from the underlying platform
  - So React applications can target platforms that don't use a DOM
- `render` inserts the rendered component to the matched element

---
## Props

- Props (properties) are data passed into a component from a parent component
- Used to dynamically change what a component renders or how it behaves

- Component definition:

```js
export const Greet = (props) => <div>Hello {props.company}</div>;
```

- Component use:

```js
<Greet company="Rangle.io" />
```

- Result:

```html
<div>Hello Rangle.io</div>
```

---
## Props, Destructuring and JSX

```js
export const Greet = ({ company }) => <div>Hello {company}</div>;
```

- We can use *destructuring assignment* to get specific fields of props
- And use `{}` to embed an expression within JSX blocks
  - Yes, the over-use of notation is confusing
- Embedded expressions are automatically escaped
- Any JavaScript expression works, even function calls
- Be careful *not* to call functions with side-effects

---
## Styling

- FIXME: explain `className`
