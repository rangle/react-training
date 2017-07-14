---
layout: page
permalink: /redux-async/
---

---

## Things Take Time

- Network and disk access take time
- We have ignored this so far


```js
  componentDidMount() {
    apiCall("https://jsonplaceholder.typicode.com/users").then(
      response => this.setState({ robots: response, isPending: false })
    );
  }
```

- Dispatch *initiation* and *completion* of HTTP request as separate Redux actions
  - Completion can be success or failure

---

## Defining Operations

- Modify `constants.js` to define names for
  - request has started
  - request completed successfully
  - request failed

```js
export const CHANGE_SEARCHTERM = 'CHANGE_SEARCHTERM'

export const REQUEST_ROBOTS_PENDING = 'REQUEST_ROBOTS_PENDING'
export const REQUEST_ROBOTS_SUCCESS = 'REQUEST_ROBOTS_SUCCESS'
export const REQUEST_ROBOTS_FAILED = 'REQUEST_ROBOTS_FAILED'
```

---

## Asking for Robots

- Define a function to:
  - Tell the Redux store that we've asked for robots
  - Tell it that we've had a response of some kind

```js
export const requestRobots = () => {
  return (dispatch, getState) => {
    dispatch({ type: REQUEST_ROBOTS_PENDING })
    apiCall('https://jsonplaceholder.typicode.com/users')
      .then(data => dispatch({ type: REQUEST_ROBOTS_SUCCESS, payload: data }))
      .catch(err => dispatch({ type: REQUEST_ROBOTS_FAILED, payload: err }))
  }
}
```

- Note that this *doesn't* actually make a request
- It returns a function that makes a request and handles the response

---

## Map State to Properties

- Modify `mapStateToProps' in `App.js`
  - Is a request pending?

```js
const mapStateToProps = state => {
  return {
    searchTerm: state.robotsSearch.searchTerm,
    robots: state.robotsRequest.robots,
    isPending: state.robotsRequest.isPending
  };
};
```

---

## Map Dispatch to Properties

- Add a key `onRequestRobots` to component's properties
- FIXME: why does `requestRobots` only take one parameter below?

```js
const mapDispatchToProps = dispatch => {
  return {
    onSearchChange: event => dispatch(setSearchTerm(event.target.value)),
    onRequestRobots: () => dispatch(requestRobots(dispatch))
  };
};
```

---

## Initial Display

- When the component is mounted, ask for some robots

```js
class App extends Component {
  componentDidMount() {
    this.props.onRequestRobots();
  }

  // ...rendering...
}
```

---

## Rendering

- If the request is pending, tell the user that
- Otherwise, display the robots

```js
class App extends Component {

  // ...componentDidMount...

  render() {
    const { robots, isPending, searchTerm, onSearchChange } = this.props;
    const filteredRobots = robots.filter(
      robot => robot.name.toLowerCase().includes(searchTerm.toLowerCase())
    );
    return (
      <div className="tc">
        <h1>RoboDex</h1>
        <SearchBox onSearchChange={onSearchChange} />
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

---

## Reducing

- Review the reducer for handling the search term in `reducers.js`

```js
const initialState1 = {
  searchTerm: ''
}

export const robotsSearch = (state=initialState1, action={}) => {
  switch (action.type) {
    case CHANGE_SEARCHTERM:
      return Object.assign({}, state, {searchTerm: action.payload})
    default:
      return state
  }
}
```

---

## Reducing (cont.)

- Add a separate reducer for handling the state of the robots
- Redux allows us to combine orthogonal reducers

```js
const initialState2 = {
  robots: [],
  isPending: true
}

export const robotsRequest = (state=initialState2, action={}) => {
  switch (action.type) {
    case REQUEST_ROBOTS_PENDING:
      return Object.assign({}, state, {isPending: false})
    case REQUEST_ROBOTS_SUCCESS:
      return Object.assign({}, state, {robots: action.payload, isPending: false})
    case REQUEST_ROBOTS_FAILED:
      return Object.assign({}, state, {error: action.payload})
    default:
      return state
  }
}
```

- And yes, we should choose better names than `initialState` and `initialState2`
- FIXME: why is the initial state `isPending: true` when `REQUEST_ROBOTS_PENDING` is `isPending: false`?
