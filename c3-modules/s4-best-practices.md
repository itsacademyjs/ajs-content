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