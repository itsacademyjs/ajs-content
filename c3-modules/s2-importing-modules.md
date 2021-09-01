
## Importing Modules

The main way of importing a module into a current file is by using the Node.js require function.

There are three kinds of modules in Node.js:
1. Core Modules
2. File Modules
3. External Node Modules or NPM Modules
   
All the above mentioned modules use the `require()` function. When we make a require call with a relative path for example, `require('./filename')` or `require('../foldername/filename')` Node.js runs the destination JavaScript file in a new scope and returns whatever was the final value for `module.exports` in that file.
