---
layout: lesson
title: "Introduction to React"
permalink: /a0-react-intro/
---

---
## What is React?

- A Javascript UI framework based on declarative views
- Core principle: generate page with nested function calls that take data as input and produce HTML as output

---
## Why React?

- Older UI frameworks built DOM trees imperatively
- E.g. [jQuery](https://jquery.com/)

```js
$('.more-detail').click(function() {
    var scheduleId = $(this).data('id');
    $.get(
        '/schedule/' + scheduleId,
        function(res) {
            $('.schedule-detail-body').append(res);
        },
        'html')
});
```

- Data had to be stored on the HTML element as an attribute
- `$.get` call is asynchronous
- Requires that HTML initially be created on the server

---
## What's Wrong With This?

- Views and models are tightly coupled
  - We are trusting the DOM to be in a certain state when the `GET` request completes
  - Which makes combining components hard
- The more HTML is generated on the server, the harder it is to handle a variety of devices
- State needs to be well understood by the developer
  - More specifically, the *entire* DOM tree needs to be understood rather than just a small chunk
- View implementation details retained in different parts of the codebase make it more difficult to maintain
- Scales poorly: updates are slow, and get slower as the application becomes more complex

---
## Enter React

- DOM nodes are no longer a source of data
- Declarative view rendering and composition removes the need to understand DOM state when updating views
- View implementation details are easier to modularize
- It's faster: React only re-renders those parts of the view that need to be updated
