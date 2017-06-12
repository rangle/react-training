---
layout: lesson
title: "Lifecycles"
permalink: /a6-lifecycles/
---

# Lifecycle Methods

---

# Categories

TODO: Replace this diagram with a Rangle version

http://www.codevoila.com/uploads/images/201607/reactjs_component_lifecycle_functions.png

---

## Mounting

When a component is created and inserted into the DOM.

- `constructor`: When a component is created. Do basic state initialization here.

- `componentDidMount`: Called after a component has finished mounting. Ajax calls that can cause component re-renders should go here.

- `componentWillMount`: Called during server rendering. Use constructor otherwise.

---

## Updating

When a component's props or state has changed.

- `shouldComponentUpdate`: Called after a component's props or state has changed. Decides whether or not a component should re-render. Main use is performance optimization.

- `componentWillUpdate`, `componentDidUpdate`: Called before and after a component re-renders. Any manual work done outside of React in whenever updates happen should be done here. ie. encapsulation of 3rd party UI libraries within a component.

- `componentWillReceiveProps`: Called before a component's has received props whose values have changed.

--

## Unmounting

When a component is destroyed and removed from the DOM.

- `componentWillUnmount`: Called when a component is destroyed and removed from the DOM. Do any clean up here ie. remove 3rd party listeners, unsubscribe, etc.
