---
layout: page
permalink: /react-lifecycles/
---

---

## What Do We Mean by "Lifecycle"?

- Lifecycles are phases of an object's existence where we might want to add or replace logic

![Lifecycle Methods]({{"img/reactjs_component_lifecycle_functions.png"|absolute_url}})

FIXME: Replace [this diagram](http://www.codevoila.com/uploads/images/201607/reactjs_component_lifecycle_functions.png) with a Rangle version

---

## Mounting

- This group called when a component is created and inserted into the DOM
- `constructor`: when a component is created
  - Do basic state initialization here
- `componentDidMount`: called after a component has finished mounting
  - AJAX calls that can cause component re-renders should go here
- `componentWillMount`: called during server rendering
  - Use constructor otherwise.

---

## Updating

- This group called When a component's props or state has changed.
- `shouldComponentUpdate`: called after a component's props or state has changed.
  - Decides whether or not a component should re-render
  - Main use is performance optimization
- `componentWillUpdate` and `componentDidUpdate`: called before and after a component re-renders
  - Any manual work done outside of React when updates happen should be done here
  - E.g., encapsulation of 3rd party UI libraries within a component
- `componentWillReceiveProps`: called before a component has received props whose values have changed

---

## Unmounting

- Called when a component is destroyed and removed from the DOM
- `componentWillUnmount`: do clean-up here
  - E.g., remove 3rd party listeners, unsubscribe, etc.

---

## Using These

```js
class App extends Component {
  constructor() {
    // as before
  }

  componentDidMount() {
    apiCall("https://jsonplaceholder.typicode.com/users")
      .then(response =>
        this.setState({
          robots: response,
          isPending: false
        })
      )
  }
}
```

```js
export const apiCall = (link) =>
  fetch(link).then(response =>
      response.json()
  )
```
