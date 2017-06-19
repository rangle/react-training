---
layout: lesson
title: "Making Connections"
permalink: /b4-connect/
---

-   connect the app to Redux

-   connect() is optimized in order to avoid store.subscribe() on the component.

-   Make App redux aware (App.js)
    -   Add an import for the actions
    -   Add mapStateToProps(state) - What part of the store the container cares about.
        -   Hookup searchTerm from store
    -   Add mapDispatchToProps(dispatch) In addition to reading the state, container components can dispatch actions. In a similar fashion, you can define a function called mapDispatchToProps() that receives the [dispatch()](http://redux.js.org/docs/api/Store.html#dispatch) method
        -   Hookup the setSearchTerm action to accept an event object and pass into the action e.target.value
    -   Add connect() to default export
    -   It might be worth mentioning the mergeProps param of connect
    -   Remove the searchTerm from state
    -   Inside render()
        -   remove the searchterm from this.state
        -   add searchterm from props
        -   Remove the onSearchChange()
        -   Replace the render reference to this.props.onSearchChange
    -   Since we're now using Props instead State, update propTypes
