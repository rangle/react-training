---
layout: lesson
title: "Creating a Card List"
permalink: /a4-cardlist/
---

- Copying and pasting cards is tedious, so we create a `CardList` component
- Hard-code the data as an array in `robots.js` to start with

```js
export const robots = [
  {
    id: 1,
    name: 'Leanne Graham',
    username: 'Bret',
    email: 'Sincere@april.biz'
  },
  ...
}
```


- Then pass that array to `CardList` in `index.js`

```js
ReactDOM.render(
  <div>
    <CardList robots={robots} />
  </div>,
  document.getElementById('root')
);
```

- `CardList` transforms the array of values into an array of views using `map`
  - Wraps that array in a `div` because it can only return one thing
  - JSX automatically concatenates array elements for us

```js
import React from 'react';
import Card from './Card';

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

CardList.propTypes = {
  robots: React.PropTypes.array.isRequired
};

export default CardList;
```
