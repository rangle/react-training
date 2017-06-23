---
layout: page
permalink: /react-container/
---

---

## Goals

- Create a `SearchBox` component to list only robots that match the search term
- Key inputs are handled by `SearchBox`, but robots are being provided by parent component
  - We need some way to integrate the two
- Solution:
  - Make the search box and display stateless (display) components
  - Use the parent as a common third party to hold the data

---

## Main Application

```js
class App extends Component {
  constructor() {
    super()
    this.state = {
      searchTerm: "",
      robots: robots
    }
  }
  onSearchChange = (evt) => {
    this.setState({searchTerm: evt.target.value})
  }
  render() {
    const { searchTerm, robots } = this.state;
    const filteredRobots = robots.filter(robot =>
      robot.name.toLowerCase().includes(searchTerm.toLowerCase())
    );
    return (
      <div className="tc">
        <h1>RoboDex</h1>
        <SearchBox onSearchChange={this.onSearchChange}/>
        <CardList robots={filteredRobots} />
      </div>
    );
  }
}
```

---

## How It Works

- Note how `onSearchChange` is passed down to `SearchBox`
  - Remember, every `setState` call triggers re-rendering
  - `SearchBox` doesn't need to care *whose* state it is updating
- Also note how `filteredRobots` is set by filtering entire robot list
  - Do *not* modify the main list, since we don't want to throw robots away
  - Again, `CardList` doesn't care which list it is displaying

---

## Search Box

```js
const SearchBox = (props) => {
  const { onSearchChange } = props;
  return (
    <div className="pa2">
      <input className="pa2"
        type="search"
        placeholder="search Robots..."
        onChange={onSearchChange}
      />
    </div>
  );
};
```

- In principle, this is re-rendered on each keystroke because of the parent's state change
  - React does work behind the scenes to minimize work
