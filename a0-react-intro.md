---
layout: lesson
title: "Introduction to React"
permalink: /a0-react-intro/
---

# Rangle React Training

FIXME

---

## Instructors

FIXME

---

## Agenda

FIXME

---

## What is React?

- Javascript UI framework
- Declarative views
- Centered around small building blocks and combining those to build larger ones

---

## Why do we need React?

- Before reactive UI frameworks were around, DOM trees had to be put together imperatively

- Eg. jQuery

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
- $.get call is asynchronous, we are trusting that the state of the DOM to look a certain way when the GET request completes
- Requiring that HTML be rendered on the server


## What's wrong with this?

There are some problems with this setup:
- View and model layers are coupled
- State needs to be well understood by the developer when doing manual DOM manipulation, requires understanding of entire DOM tree rather than just being worried about your small chunk
- View implementation details retained in different parts of the codebase make it more difficult to maintain
- Scales poorly with application complexity
- Updates are slow

## Why do we need React?

- DOM nodes are no longer a source of data
- Declarative view rendering and composition remove the need to understand DOM state when updating views
- View implementation details are less spread out
- Quicker render times due to React only re-rendering parts of the view that need to be updated
