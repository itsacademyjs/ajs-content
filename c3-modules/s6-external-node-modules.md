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