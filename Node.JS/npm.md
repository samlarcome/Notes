# Node Package Manager (npm)

## Package Management
  - Dependencies are usually installed in packages handled by a package manager
  - A package manager will do the following:
    - download and install packages to be used as dependencies on a project
    - check packages for any vulnerablilites
    - check if packages can be updated 
    - handle a packages sub-dependencies (if any)
    - remove all files of a package when no longer needed
    - provides repeatable and consistent process of installing dependencies

  - Node package manager's cli command (**npm**) is included in the Node.js installation
  - ```npm -v``` will check version of npm

## Initialization
  - To initialize a Node.js app, we enter ```npm init``` into the terminal
  - We should get a prompt asking us for information about project
    - Can skip this by entering ```npm init -y```
  - Will get a 'package.json' file when prompt is complete
  ```
  {
    "name": "test",
    "version": "1.0.0",
    "description": "a test",
    "main": "index.js",
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
    },
    "author": "joe mama",
    "license": "ISC",
    "dependencies": {
      "express": "^4.17.1"
    },
  }
```
  - File will update when you download more dependencies

## Installing
  - To install nodemon, for example, we could enter ```npm i nodemon``` or ```npm install nodemon```
  - Newly installed packages will be added to the 'package.json' file
  ```
    "dependencies": {
      "express": "^4.17.1",
      "nodemon": "^2.0.13"
    }
  ```

## Package Scopes
  - Most packages should be installed locally
  - That way each project can control what version it uses

 ### dev dependencies
  - Used for the purpose of making development easier and more efficient
  - Make developer's lives easier, but makes no changes to the app itself
  - To install developer dependencies: ```npm install nodemon --save-dev```
  - Listed in the package.json file, and are not included in production release of the project
  ```
    "dependencies": {
      "express": "^4.17.1"
    },
    "devDependencies": {
      "nodemon": "^2.0.13"
    }
  ```
 ### Global Packages
  - Packages can be installed globall, or system wide: ```npm install http-server -g```
    - Do not need to install for each new project
  - Typically, these will be used in the cli rather than imported into project's code
  - Won't be in the package.json file, rather a separate directory
