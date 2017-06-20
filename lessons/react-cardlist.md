---
layout: lesson
permalink: /react-cardlist/
---

---

## Goals

- Copying and pasting cards is tedious, so we create a `CardList` component
- Hard-code the data as an array in `robots.js` to start with

```js
export const robots = [
  {
    id: 1,
    name: "Leanne Graham",
    username: "Bret",
    email: "Sincere@april.biz"
  },
  ...
}
```

---

## Connecting the Pieces

- Then pass that array to `CardList` in `index.js`

```js
ReactDOM.render(
  <div>
    <CardList robots={robots} />
  </div>,
  document.getElementById("root")
);
```

---

## The Card List

- `CardList` transforms the array of values into an array of views using `map`
  - Wraps that array in a `div` because it can only return one thing
  - JSX automatically concatenates array elements for us

```js
const CardList = ({ robots }) => {
  const cardsArray = robots.map(robot => (
    <Card
      name={robot.name}
      email={robot.email}
      id={robot.id} />
  ));

  return (
    <div>
      {cardsArray}
    </div>
  );
};
```

---

## PropTypes

- Tell React that the `robots` array is required

```js
CardList.propTypes = {
  robots: React.PropTypes.array.isRequired
};
```
