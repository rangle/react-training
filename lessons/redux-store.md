---
layout: page
permalink: /redux-store/
---

---

## The Goal

- Create a store using `react-redux` to manage everything
- Put it in `index.js`
- Wrap it in a `Provider` element from `react-redux`

```js
// ...as before...
import robotsSearch from './reducers'
import { createStore } from 'redux'
import { Provider } from 'react-redux'

const store = createStore(robotsSearch)

ReactDOM.render(
  <Provider store={store}>
    <App/>
  </Provider>,
  document.getElementById('root')
);
```

- `createStore` creates a Redux store
  - We still need to provide specific actions and dispatchers
- `Provider` is a way to create the equivalent of a global variable
  - Adds named data to the props of all of the elements within its scope
- We won't actually refer to `store` ourselves
  - It will be connected when we wire everything together

---

## Connecting the Pieces

- Modify `App.js` (our container)
- `connect` takes two functions
- Wraps the `App` class with something that knows how to talk to a default store
  - This code relies on the `store` variable created by the `Provider`

```js
// ...as before...
import { connect } from "react-redux";
import { setSearchTerm } from "../actions";

// ...map state to properties...

// ...map dispatch function to properties...

class App extends Component {
  // ...constructor...
  // ...initial data fetch...
  // ...render...
}

export default connect(mapStateToProps, mapDispatchToProps)(App)
```

---

## Mapping State to Properties

- Given a state, generate the change to the properties

```js
const mapStateToProps = state => {
  return { searchTerm: state.searchTerm };
};
```

---

## Mapping Dispatch Function to Properties

```js
const mapDispatchToProps = dispatch => {
  return {
    onSearchChange: event => dispatch(setSearchTerm(event.target.value))
  };
};
```

---

## Constructor

- Initialize state as usual

```js
class App extends Component {
  constructor() {
    super()
    this.state = { robots: [], isPending: true }
  }
}
```

---

## Initial Data Fetch

- As before

```js
  componentDidMount() {
    apiCall("https://jsonplaceholder.typicode.com/users").then(
      response => this.setState({ robots: response, isPending: false })
    );
  }
```

---

## Rendering

- Looks pretty much the same as well
  - Which is the point
- Get `onSearchChange` from the properties
  - This is the function named in the object returned by `mapDispatchToProps`
  - `react-redux` wires all of this up for us

```js
  render() {
    const { robots, isPending } = this.state;
    const filteredRobots = robots.filter(
      robot => 
        robot.name.toLowerCase().includes(this.props.searchTerm.toLowerCase())
    );
    return (
      <div className="tc">
        <h1>RoboDex</h1>
        <SearchBox onSearchChange={this.props.onSearchChange} />
        <Scroll>
          {
            isPending
              ? <h2>Loading...</h2>
              : <CardList robots={filteredRobots} />
          }
        </Scroll>
      </div>
    );
  }
}
```
