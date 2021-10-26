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
