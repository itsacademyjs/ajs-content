

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
