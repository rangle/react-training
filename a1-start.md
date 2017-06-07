---
layout: lesson
title: "Getting Started"
permalink: /a1-start/
---

## Requirements

- Need the latest Long-term Support version of Node.js
    - Install using NVM (Mac/Linux)
    - Installer from Nodejs.org (all)

- A code editor, ie: Visual Studio Code

- Create React App command line tool
    `npm install --global create-react-app`

---

## Create React App

- Command line tool that creates a React application with the basic necessities including dependencies
- `create-react-app Robodex`: creates the app in the folder _Robodex_
- `package.json`: information on what dependencies your application has as well as some simple commands you can run
- `README.md`: documentation on React and create-react-app
- `node_modules`: dependency files
- `src`: application source files
- `public`: the build target path

---

## Create React App Commands

- __start__: serves the application in a develoopment environment. code changes will refresh the browser
- __build__: builds the application and copies the files to the _public_ folder
- __test__: runs the application tests
- __eject__: ejects the build configuration, only for advanced users who need customization
