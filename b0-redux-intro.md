---
layout: lesson
title: "Introduction to Redux"
permalink: /b0-redux-intro/
---

Before starting into this content, it is a good idea to review the app as it is, and cover the basics at a high level again to refresh the audience.

Why use Redux?

-   Good for managing large state. React afterall, is just a view layer.

-   Do one thing really great; React does views really well; Redux handles state really well

-   Redux can manage state without managing a view

-   When projects become large, they need to share state between containers; redux solves this by providing a global state

-   Redux provides a framework for managing global state

-   Useful for sharing data between containers

-   Predictable state management using the 3 principles

-   Encourages the use of Immutability to help prevent unexpected errors

-   Easy to debug state-related issues

-   Manage state when your app becomes too big for it to just use setState()

The 3 principles

-   Single source of truth

-   State is read only

-   Changes are made using pure functions

Flux

-   Diagram showing dispatcher, action, etc.

-   Facebook created it

-   Unidirectional data flow

What is Redux?

-   A creation by Dan Abramov

-   Like a model layer (the ‘M' in MVC)

-   Implementation of flux architecture

-   Larger, global version of this.state

Redux Lingo

-   Action

-   Dispatch

-   Reducer

-   Store

Folder structure

-   Containers

-   Components

-   Reducers

-   Actions

-   Constants

Live coding

-   Clone the robodex repo and start it running
    -   Git clone
        <https://github.com/aneagoie/react-training-RoboDex>
    -   Npm install
    -   Npm start
