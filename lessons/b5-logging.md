---
layout: lesson
title: "Redux Logging"
permalink: /b5-logging/
---

Now that we have a redux application running; how do we know what is
firing? What data is being passed? How would we debug any errors in
redux? The redux logger!

-   Install the logger via npm install redux-logger --save

-   Open the index.js file and add:

```
import createLogger from ‘redux-logger';
```

-   Create an instance of the logger by calling createLogger():

```
const logger = createLogger();
```

-   Ensure the applyMiddleware function is imported from redux

-   Update the createStore call to add a second argument:
    -   applyMiddleware(logger)
    -   So that it looks like:

```
const store = createStore(rootReducer, applyMiddleware(logger))
```

-   Now load the app and show the logs in the console
