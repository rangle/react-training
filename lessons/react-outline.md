---
layout: page
permalink: /react-outline/
---

---

## Goal

- We are going to make a Robodex

![Robodex Screenshot]({{'img/robodex-screenshot.png'|absolute_url}})

---

## Creating a Card

- Delete `HelloComponent` and start building the app with a `Card` component
- Start by creating `Card` as a stateless component in `Card.js` with hardcoded mock data

```html
<div>
    <img alt="photo" src="https://robohash.org/test?size=200x200"/>
    <div>
        <h2>Jane Doe</h2>
        <p>jane.doe@gmail.com</p>
    </div>
</div>
```

- Convert the hard-coded values into `id`, `name`, and `email` props

---

## Customizing the Cards

- Then add JSON data to make each card different
  - `robots.js` is available from the lesson 3 folder in the repo
- Use destructuring to get values out of props

---

## Static Checking with PropTypes

- Install `prop-types` package and implement this:

```js
Card.propTypes = {
    id: React.PropTypes.number.isRequired,
    name: React.PropTypes.string.isRequired,
    email: React.PropTypes.string.isRequired
};
```

- Checks the properties being passed into components

---

## Styling

- Add classes to the `Card` component

```html
<div className="bg-light-green dib br3 pa3 ma2 grow">
    <img role="presentation" src={`//robohash.org/${id}?size=200x200`} />
    <div>
        <h2>{name}</h2>
        <p>{email}</p>
    </div>
</div>
```

- Note use of back-quoted string as `src` attribute of `img`
  - JavaScript string interpolation
- But no quotes around the overall expression
  - JSX does that for us
- Side note: the `src` URL doesn't have a protocol
  - It will use HTTP or HTTPS depending on what the page used
