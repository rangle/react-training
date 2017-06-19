---
layout: lesson
title: "Merging"
permalink: /b7-merge/
---

-   We're going to leverage mergeProps to help us with filtering robots

-   Open App.js and create a new function called mergeProps() that will take in two params, one for state props and one for dispatch props

-   Return all the state props and dispatch props along with a new one for filteredRobots that will apply searchTerm to robots data

-   Update the connect to pass mergeProps as the third param

-   Now update the render method to remove robots from props destructuring and add filteredRobots instead. Now you can remove the following lines for calculating filteredRobots
