---
layout: lesson
title: "Getting Started"
permalink: /a1-start/
---

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

- Use `npm command` to run
- `start`: serves the application in a development environment
  - Code changes are automatically refreshed in the browser
- `build`: builds the application for deployment and copies the files to the `public` folder
- `test`: runs the application's tests
- `eject`: ejects the build configuration
   - Only for advanced users who need customization
