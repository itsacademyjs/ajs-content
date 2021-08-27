# Modules

When building an application, your code can become more and more complex. Putting all this code in one file is certainly not the best option. We need a way of encapsulating complexity to successfully deliver large applications and work in sizable teams. 

JavaScript was originally designed to be read from top to bottom in a simplistic manner by a web browser, and files were
loaded using <script> tags. As the applications written in JavaScript got larger and larger, two module systems were developed i.e. AMD and CommonJS, to make code more manageable and reusable.

These two systems exist because the browser and the server offer different challenges in terms of module-loading latency (network requests vs. file system).


## Understanding the Module System

In 2009, Kevin Dongaoor created CommonJS with the goal to specify an ecosystem for JavaScript modules on the server. NodeJS follows the CommonJS module specification. 

Here are important features of the module system:

- Each file is its own module.
- Using the module variable, each file has access to the current module definition.
- To export a current module we use `module.exports`. 
- To import a module, we use the globally available `require function`.

## Defining a Node Module and Creating Our Own Custom Modules

What is a module?

A module can either be a single file or a directory containing one or more files. In simple terms, a module is a JavaScript file.

With the modular functionality that Node provides, we can import our own external files, core node modules also known as native node modules, and NPM modules. 

The `module.exports` is a special object which is included in every JavaScript file in the Node.js application by default. The current module is represented by the variable module and exports is the object that will be exposed as a module. This means that whatever gets assigned to `module.exports` will be exposed as a module.

In this lesson, we are going to be looking at how we can export and import our own files.

For example, there are two files, `message.js` and `index.js` in the same directory. `message.js` is the file from where you export and `index.js` is the file to where you will import that file. 

Since exports is an object and whatever you assign to it gets exposed as a module, if you assign a string literal then it will expose that string literal as a module.

*Illustration*

```
// message.js

module.exports = "Hello World!";
```


```
//index.js

var msg = require('./message');
console.log(msg);
```

When you run the above example we get,

```
C:\> node index.js
Hello World!
```
Here we export a string literal, "Hello World!" using `module.exports` and then this string literal gets imported to `index.js` using the require method. 

**Note:** To import a local module you must specify `./` as a path of root folder. However, you **do not** need to specify the path to import NodeJS core modules or NPM modules in the require function. We will look into these later in this lesson.

Example to export a function called "multiply" from a file called `calculate.js`. We simply assign it to `module.exports`.

```
// Exporting file calculate.js

const multiply = (number1, number2) =>{
    return number1*number2;
}

module.exports = multiply;
```

The function "multiply" gets imported using the `require()` method. We can now call this function in a different file, `index.js` by passing the arguments as shown. 


```
// index.js

const multiply = require('./calculate');
const result = multiply(2,2);
console.log(result); //logs out 4
```

Example to export an entire object called multiply and access the different methods in it.

```
//Exporting object multiply from file calculate.js

const multiply = {
    result : (number1, number2) => {
        return number1 * number2;
    }
}
module.exports = multiply;
```

Importing object multiply into our `index.js` file using `require()` method.

```
// index.js

const multiply = require('./calculate')

const result = multiply.result(5,2)

console.log(result) // logs out 10
```

We access the result method of the multiply object using the `.` dot operator.

Example to export only the method of an object. This is good pratice when you only want to require some methods/functions of an object and not the enitre object. This would make your code more secure.

```
// Exporting result method of multiply object in calculate.js

const multiply = {
    result : (number1, number2) => {
        return number1 * number2;
    }
}

module.exports = multiply.result;
```

```
//  index.js

const add = require('./calculate')
const result = multiply(5,2)
console.log(result) //logs out 10
```

Example to export a function constructor.

A function constructor is used to create a new instance of an object which has the same properties as that of the main object or function.

```
// Exporting a function constructor in calculate.js

function Multiply (){
    this.result = (number1, number2) => {
        return number1 * number2;
    }
}

module.exports = new Multiply();  
```

The process of creating an instance of an object is called instantiation. Here in the above example, by using the `new` keyword, we create a new instance of the 'Multiply' object. 

```
//index.js 

//Importing the function constructor and accessing the result method inside it. 

const multiply = require('./calculate');
const result = multiply.result(2,3)
console.log(result); //logs out 6
```

There is another way to import and export a function constructor. This can be done by creating our new instance in the main file (example, `index.js`) rather than in the exported file `calculate.js` as shown above `module.exports = new Multiply()`. This can be seen when we export ES6 classes which work similar to function constructors.


You might be familiar that classes are special functions. They are templates for creating objects. They enclose data with code to work on that data. To declare a class you use the `class` keyword and then we use a special method `constructor` for creating and initializing an object created with a class.

```
//Exported file calculate.js

const Multiply = class{
    constructor(number1, number2){
        this.number1 = number1;
        this.number2 = number2;
    }

    result(){
        return this.number1 * this.number2;
    }
}

module.exports = Mulitply;
```

In the imported file i.e. `index.js` we create a new instance and access the result method to get our calculated result.

```
// Imported file index.js

const multiply = require('./calculate');
const result = new multiply(3,3);
console.log(result.result()); //logs out 9
```

## Importing Modules

The main way of importing a module into a current file is by using the Node.js require function.

There are three kinds of modules in Node.js:
1. Core Modules
2. File Modules
3. External Node Modules or NPM Modules
   
All the above mentioned modules use the `require()` function. When we make a require call with a relative path for example, `require('./filename')` or `require('../foldername/filename')` Node.js runs the destination JavaScript file in a new scope and returns whatever was the final value for `module.exports` in that file.

## Exporting Modules

Let's take a deeper look at `module.exports`.

We know that in Node.js each file is a module. Whatever be the item that you want to export should be assigned to `module.exports` variable. It is important to note that in every file, the `module.exports` is already defined to be a new empty object by default.

This means that module.exports = { } is implicitly present and by default every module exports an empty object i.e. { }

For example:

```
app.js

console.log(module.exports); // logs out: { }
```

Up until now, we have only been exporting a single object from a module by assigning the object to module.exports. More often than not, it a common requirement to export more than one variable from a module.

There are many ways of achieving this. We will discuss them with code examples.

Example 1: 

```
// Exported file foo1.js

var x = function() {
    console.log("x called");
};

var y = function() {
    console.log("y called");
}

module.exports = {
    x: x,
    y: y
};
```

In the above example, function 'x' is defined earlier than the point at which we actually export it to other files. 

This becomes quite cumbersome to manage because, in terms of lines, what the module returns can potentially be distant from what the module contains.


Example 2:

Since in Node.js module.exports is by default set to an empty object { }, a common convention is to simply attach the objects to export to module.exports inline. 

```
// Exported file foo2.js

module.exports.x = function () {
    console.log("x called");
};

module.exports.y = function () {
    console.log("y called");
};
```

Since typing `module.exports` all the time can become tiresome, Node.js helps us by creating an alias for `module.exports` called `exports`. This means instead of typing `module.exports.x` you can now simply use `exports.x`. However, if you want to assign a single export, use `module.exports`.

So this brings us to our example 3:

```
// Exported file foo3.js

exports.x = function () {
console.log('x called');
};

exports.y = function () {
console.log('y called');
};
```

It is important to note that `exports` is just like any other JavaScript variable. Node.js simply does `exports = module.exports` for us. So, when we add 'year' to exports we say `emports.year = 2021`, since JavaScript variables are references, here we are effectively doing `module.exports.year = 2021`. 

However, `exports = 2021` will break the reference to `module.exports`. This does not make `module.exports = 2021`. Note that you should only use the `exports` alias to attach and not directly assign things to it.

Finally, you execute `app.js` to demonstrate that from the import point of view, all the methods in example 1, 2 and 3 are equivalent.

```
//Import file app.js

var foo1 = require('./foo1');
foo1.x();
foo1.y();
var foo2 = require('./foo2');
foo2.x();
foo2.y();
var foo3 = require('./foo3');
foo3.x();
foo3.y();
```

## Best Practices for Modules

Now that we've understood the technology behind the Node.js module system it is important for us to look at a few best practices and conventions followed by the community.

### Do Not Use the .js Extension

Although `require('./foo')` and `require('./foo.js')` both work just fine for Node.js, it is better to use `require('./foo')`.

**Reason**: In browser-based module systems since we cannot look at the server filesystem, it is assumed that you do not provide the `.js` extension.
So, to maintain the consistency, it is best pratice to avoid `.js` extension in all your require calls.

### Relative Paths

You need to use relative paths while using file-based modules. Use `require('./foo')` instead of `require('foo')`.

**Reason**: Non-relative paths are reserved for core modules and external node modules.

### Utilize exports

As dicussed earlier, whenever you want to export more than one thing, try to use the `exports` alias.

**Reason**: `exports` keeps what is exported close to its definition. It is also conventional to have a local variable for each thing you export so that you can use it locally.

Here's how you would create a local variable and easily export:

```
var foo = exports.foo = /* anything you want to export as 'foo' from this module */
```

### Export an Entire Folder

When you have many modules that go together that you keep importing into other files, it is best practice to avoid repeating huge import blocks.

For example:

```
var foo = require('../foldername/foo');
var bar = require('../foldername/bar');
var bas = require('../foldername/bas');
var qux = require('../foldername/qux');
```

A preferable alternative would be to create a single `index.js` in the directory 'foldername'.

For example:

```
// index.js

exports.foo = require('./foo');
exports.bar = require('./bar');
exports.bas = require('./bas');
exports.qux = require('./qux');
```

After having imported all the modules once and exported them from `index.js` you can simply import this `index.js` whenever you need all these things.

For example:

```
var something = require('../foldername/index);
```

**Reason**: To export, you just need to create an `index.js` file. Individual modules (files) remain smaller because you do not need to put everything into a single file to be able to import it easily elsewhere. On the import side, you have a fewer require calls to write. This makes it more maintainable.


## Core Modules or Native Modules

### Importing Core Modules

You have already come across some modules that don't need to be imported. For example, we have used the `console` module many times without requiring it in our own local files. This because it is available globally.

Importing core modules is very similar to importing file-based modules that we've written. We still use the require function. The only difference is, instead of a relative path to the file, you simply specify the name of the module to the `require()` function. 

For example, to import the core path module, you write a statement as, `var path = require('path')`. There is no implicit global
namespace pollution and what you get is a local variable that you name yourself to access the contents of the module. For example, in `var path =require('path')` we are storing it in a local variable called `path`.


We're going to discuss some important core modules, but you can find the entire list [here](https://nodejs.org/dist/latest-v15.x/docs/api/).

### Path Module

We use `require('path')` to import this module. The path module exports functions that provide useful string transformations common when working with the file system.The primary use of path is, it removes the inconsistencies in handling file system paths. For example, `path.join` uses the forward slash `/` on UNIX-based systems like Mac OS X vs. backward slash `\` on Windows systems. 

Here's a quick look at some more useful functions:

**dirname, basename, and extname**

These functions are considered to be the most useful functions in the path module.

- `path.dirname` gives you the directory portion of a specific path string (OS independent). 

For example:

```
var path = require('path');

var completePath = '/foo/bar/index.html';

console.log(path.dirname(completePath)); //logs out: /foo/bar
```

- `path.basename` gives you the name of the file.

For example:

```
var path = require('path');

var completePath = '/foo/bar/index.html';

console.log(path.basename(completePath)); //logs out: index.html
```

- `path.extname` gives you the file extension.

For example:

```
var path = require('path');

var completePath = '/foo/bar/index.html';

console.log(path.extname(completePath)); //logs out: .html
```


**path.join([str1], [str2], …)**

This function joins any number of paths together, considering the operating system.

Example:

```
console.log(path.join('foo', '/bar', 'bas'));
```

Output:

```
// logs on Unix: foo/bar/bas
// logs on Windows: foo\bar\bas
```


**fs Module**

This module provides access to the file system. We use `require('fs')` to import this module. The `fs` module has functions for reading files, writing to files, renaming and deleting files.

Here's an example showing how to write to the file system and read from it:

```
const fs = require('fs');

//write
fs.writeFileSync('test.txt', 'Hey there! I am fs.');

//read
console.log(fs.readFileSync('test.txt').toString());
```

Another example:

```
// file.txt 

This is an awesome text.
```

```
// index.js

const fs = require('fs');

fs.readFile('./file.txt','utf-8',(err,data) => {
    if (err) throw err
    console.log(data);
});
```


If `fs` is not imported using the require function it will throw an error. This is because the file system `fs` module is not globally available like the `console ` module. Therefore, all the data needs to be imported from the file system module using the `require()` and stored in a variable (in our case we have used 'fs' for readability).

Using the fs variable we can access the `readFile()` method where we have passed three arguments, a file path, character encoding `utf-8`, and the callback function to give an output. The utf-8 encodes the value and gives the text as an output rather than a buffer as shown below:

`<Buffer 54 68 69 73 20 69 73 20 61 6e 20 61 77 65 73 6f 6d 65 20 74 65 78 74 2e>`

The callback function has two arguments: an error `err` and the actual data contained in the file `data` which logs out in the console.

```
//Output:

This is an awesome text.
```

The distinguished thing about the `fs` module is that it has both asynchronous as well as synchronous functions (using the `-Sync` postfix). For example, you can use `unlink` or `unlinkSync` to delete a file. The difference between the sync and asyn version is that the async version takes a callback and passes the error object if there is one. It is better to use the asynchronous functions whenever possible in busy processes such as in a web servers because accessing the filesystem synchronously blocks the JavaScript thread until the request is complete.

An example showing how to delete file using unlinkSync:

```
//deleteSync.js

var fs = require('fs');
try {
fs.unlinkSync('./file.txt');
console.log('file.txt is successfully deleted');
}
catch (err) {
console.log('Error:', err);
}
```

An example showing how to delete file using unlink:

```
//delete.js

var fs = require('fs');
fs.unlink('./file.txt', function (err) {
if (err) {
console.log('Error:', err);
}
else {
console.log('file.txt successfully deleted');
}
});
```

## External Node Modules

### Importing NPM modules

What exactly is Node Package Manager?

NPM is a package manager for external modules, modules that anybody could build so that you could incorporate into your projects.

As per the official documentation:

> NPM is the world's largest software registry. Open-source developers from every continent use npm to share and borrow packages and many organizations use npm to manage private development as well.

NPM actually get bundled with Node JS. So, when we installed Node we already installed NPM. You can check if NPM is installed on your computer by simply running the command `npm -v` on your command-prompt. If it returns some version number, then that means NPM is successfully installed.

If you head over to [npmjs](npmjs.com), you've got this huge search bar where you can search for all the packages that they contain. This free npm Registry is one of the largest software registries in the world with more than one million packages. With all the NPM modules, you can see that there's an extensive documentation on what you can do with it, how you install it and a whole bunch of other stuff.

As an example, we're going to install a superheroes package from [npmjs](npmjs.com) and include it in our project to generate superhero names. So if you click on superheroes, there's a description that tells you how to use this package. Go ahead and install it by typing, `npm install superheroes`. In order to use it, you require the module.

The superheroes module also has a `random()` method that generates as an output a superhero name.

Firstly, with an NPM module, make sure you are in the right directory and install it `npm install superheroes`. So now that you've installed go into `index.js` and require this superheroes module.


```
//index.js

var superheroes = require("superheroes");

var superheroName = superheroes.random();

console.log(superheroName);
```


So when you run, node index.js, a random superhero name logs out.



```
Output:

$ node index.js
Spider-Man
```


**Exercise:**

As a simple challenge, head over to [npmjs](npmjs.com) to install the supervillians package and incorporate it in your project to console log some supervillian names.







