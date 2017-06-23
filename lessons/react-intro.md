---
layout: page
permalink: /react-intro/
---

---

## What is React?

- A Javascript UI framework based on declarative views
- Generate page with nested function calls that take data as input and produce HTML as output

---

## What Problems Does It Solve?

- Older UI frameworks built DOM trees imperatively
  - HTML initially be created on the server
  - Data stored on the HTML elements as attributes
- A lot of re-rendering (performance penalty)
- Tied tightly to browsers (in a world with a growing variety of devices)

---

## Core Architectural Principles

- DOM nodes are no longer a source of data
- Declarative view rendering and composition removes the need to understand DOM state when updating views
- View implementation details are easier to modularize
- It's faster: React only re-renders those parts of the view that need to be updated

---

## Requirements

- Install the latest Long-term Support (LTS) version of NPM and Node v6+ from <http://nodejs.org/download/>
  - The download above should install two commands: `node` and `npm`
  - `npm` may require some extra configuration to set permissions properly

- A code editor
  - [VS Code](https://code.visualstudio.com/)
  - [WebStorm](https://www.jetbrains.com/webstorm/)
  - [Sublime Text](http://www.sublimetext.com/)
  - [Atom](https://atom.io/)

- `create-react-app` command-line tool:
   `npm install --global create-react-app`

---

## Create React App

- Command-line tool that creates a React application with a standard structure and dependencies
- `create-react-app robodex`: creates the app in the folder `robodex`
- `package.json`: information on what dependencies your application has as well as some simple commands
- `README.md`: documentation on React and `create-react-app`
  - Replace this with a description of your application
- `node_modules`: dependency files
- `src`: application source files
- `public`: the build target path

---

## Create React App Commands

- `npm start`: serves the application in a development environment
  - Code changes are automatically refreshed in the browser
- `npm build`: builds the application for deployment and copies the files to the `public` folder
- `npm test`: runs the application's tests
- `npm eject`: ejects the build configuration
   - Don't do this!
   - (for advanced users only) Don't do this *yet*
