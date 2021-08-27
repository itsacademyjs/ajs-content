Thirteen years ago before Node.js was written by Ryan Dahl, Netscape wanted to introduce and sell the first server-side JavaScript environment. Netscape’s LiveWire Pro Web could create dynamic pages. Unfortunately, Netscape LiveWire was not quite successful and server-side JavaScript wasn’t popularized.

At the beginning of 2009, Server.js was created to give JavaScript a module system. It was later renamed CommonJS and the project was to establish conventions on module ecosystems for JavaScript outside of the web browser. 

Dahl criticized the restricted possibilities of the most popular web server in 2009,  Apache HTTP Server because it had to handle a lot of concurrent connections (up to 10,000 and more) and the most common way of creating code (sequential programming) when code either blocked the entire process or implied multiple execution stacks in the case of simultaneous connection. 

Later that same year, Dahl wrote Node.js - a runtime environment for JavaScript, which combined Google’s V8 JavaScript engine, an event loop, and a low-level I/O API. 

Node.js allows JavaScript to run virtually anywhere the environment is installed. The key factor that led to the rise of Node.js was JavaScript showing the world what a modern web experience would be like.

 As many browsers competed to offer their users the best performance, the better the JavaScript engines became. This competition significantly improved the engine that Node.js was based on i.e. Chrome’s V8 which was an open-source JavaScript engine of The Chromium Project.

The release of Node.js helped to change JavaScript into more of a programming language and less of a scripting language. It was made possible by two things:

 * Callbacks for asynchronous code
 * A module system
   This allowed multiple files to be imported and exported via `require()` and `modules.exports`.

Eventually, a package manager called Node Package Manager (npm) was introduced for the runtime environment.  It was designed to simplify the installation, update, and uninstallation of packages. It made it easier for developers to publish and share Node.js packages.  Virtually, anything you could have needed was a single NPM install away.

 As a result, the transition into becoming a full-stack developer suddenly flung open the doors to just about anyone without needing to switch to other languages.

Here’s why Node.js exploded and grew: 
 * The environment made things effortless to learn. Programmers didn’t have to learn how to configure a local Apache server, XAMPP, configure their local file, as one did with LAMP.
 * The Node.js runtime environment with NPM allowed the ecosystem to proliferate making it easier for developers to rapidly prototype websites on both the frontend and backend.
 * Libraries on both the client-side and server-side became easier to publish, distribute, and concatenate together with tools such a Grunt, Gulp, Webpack, etc.