---
layout: page
permalink: /react-component/
---

---

## What Are Components?

- The core building blocks of React applications
- Views that represent some chunk of the element tree
- Generate elements during *rendering*
- Can take inputs from parent components
  - Values passed in from the outside are called *props* (short for "properties")
- Can generate a lot more than HTML
  - But we'll use that since we're doing this tutorial in the browser

---

## JSX

- Allows HTML-style tags to be freely mixed with JavaScript
- *Not part of JavaScript*
  - JSX is onverted into calls to `React.createElement` during the build step
- Can be created anywhere a JavaScript expression can be
  - Because it gets turned into pure JavaScript

---

## Creating a Component

- Create a basic "hello world" component

```js
function Greet() {
  return <div>Hello world!</div>;
}
```

- Mostly write this these days using:
  - A "fat arrow" function (which has more sensible treatment of `this`)
  - Which is assigned to a name
  - Which is a constant rather than a variable

```js
const Greet = () => {
  return <div>Hello world!</div>;
}
```

- In simple cases, can go even further and simply define the return expression:

```js
const Greet = () => <div>Hello world!</div>;
```

- In all cases, `Greet` is just a function returning text
  - JSX-to-JavaScript compilation translates `<div>...</div>` into return value
- Add an `export` statement at the bottom to make `Greet` visible to other modules
  - Part of the new-style ES6 module syntax
  - Which isn't yet supported by Node for server-side applications...

```js
export default Greet;
```
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

- The curly braces in the return value interpolate the value of `props.company` into the `div`
  - Embedded expressions are automatically escaped
  - Any JavaScript expression works, even function calls
  - Be careful *not* to call functions with side-effects
- Parent component uses:

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

- We can use *destructuring assignment* with `{}` to extract specific fields from objects
  - Not the same as the use of `{}` for interpolation

---

## Styling

- Have to use `className` instead of `class` to specify that property in JSX
  - Because `class` is a reserved word in ES6 JavaScript
- We often use [Tachyons](http://tachyons.io/) for styling rather than older packages like [Bootstrap](http://getbootstrap.com/)
  - But anything will work
