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