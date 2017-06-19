---
layout: lesson
title: "Advanced Topics"
permalink: /advanced/
---

-   Isomorphic/Universal
    -   What is it (Server-side react rendering)
    -   How it works (node instance)
    -   Benefits (SEO, Caching)
    -   Examples (Priceline hotels without prices)
    -   renderToString()

-   process.env.NODE_ENV for build/dev
    -   Good for applying dev specific middleware
    -   Mocking out data when in dev mode

-   Routing
    -   React-router vs redux-router
        -   Use react-router until you have a need for redux-router
    -   Props provided (router, location, routeParams)
    -   <Route> and <Router>

-   Unit testing (Jest)
    -   https://facebook.github.io/jest/docs/tutorial-react.html
    -   https://facebook.github.io/jest/docs/getting-started.html
    -   Explain libraries included (mocha, chai)
    -   Show example of TDD
    -   coverage

-   Styling
    -   CSS processors provided
    -   Global vs component css
    -   Autoprefixer
    -   Using className and style?
    -   Mention libraries like Radium

-   A11y
    -   What is A11y?
        -   It's short for Accessibility (starts with ‘A', then 11 chars, and ends with ‘y)
    -   React Intl:
        <https://www.npmjs.com/package/react-intl>
    -   What do you need? Translations? Locale time/money?
    -   What packages exist

-   Analytics (redux-gtm)
    -   Redux GTM:
        <https://www.npmjs.com/package/redux-gtm>
    -   React Tag Manager:
        <https://www.npmjs.com/package/redux-gtm>
    -   The package created by rangle for analytics (thomas, ken ono)
    -   Implementing google tag manager?

-   Spread operator used for passing props

-   GraphQL
    -   <http://graphql.org/learn/>
    -   Need to keep the content lean as we'll have a GraphQL workshop
    -   -   It's an open source architecture, made by facebook
    -   Client/server architecture
    -   One endpoint for all queries
    -   Server is language agnostic
    -   Needs a server and client
    -   Client can be relay or apollo
    -   Uses a typing system
    -   Introspection via __schema and __types
    -   Useful for when you don't have the ability to change the back-end
    -   Query vs Mutation (GET vs POST)
    -   @include and @skip directives
    -   Can cache using data-loader to save requests (ideal for mobile)
    -   Builds a middle layer of data, thin but meaningful through schemas
    -   Thinking in graphs, not views or endpoints
    -   Client: apollo vs relay
    -   Asynchronous; a field resolve() can return a promise
    -   Limit queries for security (use timeout, or query depth) to prevent a DDOS via a circular reference
    -   Fragments help copy/paste of templates
    -   Naming is important, as you should be backwards compatible
        -   Use object references instead of copying data into new custom fields (ie. include a Person ref, having smallThumbnail, instead of a custom field like smallPersonThumbnail)
    -   Useful for decoupling your data from the source

-   Performance
    -   Reselect
    -   Immutablejs - <https://auth0.com/blog/intro-to-immutable-js/>
    -   PureComponent vs Component - (https://facebook.github.io/react/docs/react-api.html#react.purecomponent>
    -   shouldComponentUpdate() - <https://facebook.github.io/react/docs/optimizing-performance.html>
    -   perfTools - <https://facebook.github.io/react/docs/perf.html>

-   Observables

-   Children
    -   React.Children(), map, forEach, count
    -   <https://facebook.github.io/react/docs/react-api.html#react.children>

-   Context
    -   How do use it
    -   Why you shouldn't use it

-   Middleware (promiseMiddleware, devTools)
    -   List some useful packages

-   PropTypes
    -   shape()
    -   Exporting your proptypes to import for parents

-   Redux
    -   mergeProps (as third param for connect)
    -   localStorage for persisting state
    -   Observables
    -   Reducers per field vs per container (rangle vs josep)
    -   Pass object instead of mapDispatchToProps to second param of connect
        -   Dan talks about this in his egghead videos
        -   It will wrap dispatch around each function in the values, functional composition

-   Scalability

-   Might not need Redux (in small apps)

-   It might be a good idea to use fewest smart/stateful components when early in development or a very small app

-   As an app grows in size, you'll probably want to build out more containers, smart components, to spread out the logic and data

-   Start off with reducers.js then when you need more than one reducer
    -   create a reducers folder
    -   create index.js
    -   move the reducers.js into reducers folder and rename the file
    -   Add an import statement to index.js and export default combineReducers
    -   Then for all other reducers, add a reducer js file and import statement and update combineReducers()

-   Reselect library

-   Selectors can compute derived data, allowing Redux to store the minimal possible state.

-   Selectors are composable. They can be used as input to other selectors.

-   Reselect Selectors are efficient. A selector is not recomputed unless one of its arguments change.
