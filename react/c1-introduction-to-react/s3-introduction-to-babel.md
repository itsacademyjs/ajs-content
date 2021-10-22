We will be writing our first react code inside the scripts/app.js file. But before that, right-click on the index.html file and open it with a live server. Open your Google Chrome console and type in React and press enter. This is to make sure that the React and ReactDOM variables exist. 

Now we could write JavaScript code in our app.js file. Let’s take our very first look at JSX. The JS in JSX stands for JavaScript and the X stands for XML. JSX is a JavaScript syntax extension. It is not part of the core JS language, it is provided to us by React. JSX makes working with templates much easier. You might have heard about other language extensions. For example, SCSS and LESS and language extensions for CSS that give variable support, something that is not available in plain CSS.

Here’s an example of a simple JSX template.

scripts/app.js
let template = <h1>AcademyJS Rocks!</h1>

Now here’s the exciting part. We are going to try and render this in our html file. The globally available ReactDOM variable has a render function that takes two arguments. The first one is the JSX element and the second one is the DOM element (where you would like to render the JSX element.) Make a new div in your html file as follows,

index.html
<div id=”app”></div>

Now let’s fetch this element by its id and feed it as the second and final argument to the render function of the ReactDOM object.

scripts/app.js
let approot = document.getElementById(“app”);
ReactDOM.render(template, approot);

Now you will not be able to see the “AcademyJS Rocks” text in your website yet. If you open the console, you will notice an error in the line where we defined our JSX template. This is precisely because JSX is not part of the core JS language, so Chrome’s JS interpreter is not able to make any sense of that line. 

So now, we need JSX because it makes our life easier, but our browser isn’t able to understand what JSX is. We can solve this problem by continuing to write JSX but instead of passing JSX directly to our browser, we will instead compile it down to regular boring old JavaScript. What we need is a transpiler. Enter Babel! Babel is a JS transpiler. It not only converts JSX to regular JS, but it also converts ES6 and ES7 features that aren’t implemented in some browsers, to regular JS. 

Exercise 1: Head over to www.babeljs.io and play around with Babel on the try-it-out page. See how many ES6 and ES7 features are converted into regular JS. Don’t forget to use the React preset.

Now, we paste our template definition code into the Babel compiler and see what the output is. The output is going to look something like this -

scripts/app.js
"use strict";
let template = React.createElement("h1", null, "AcademyJS Rocks!");

This is what Babel does under the hood. It takes in our JSX template and makes a call to the createElement function defined in the React variable. The createElement method takes 3 arguments. The first argument is the type of element we will be rendering on the DOM. The second is an object that contains the props that we need to send to this element. You will learn more about props soon. The last argument contains the children of this component, which in this case is just a string.

Exercise 2: Take the output from the Babel Transpiler and replace the line where we define the JSX template with it. You should now be able to see your element on your HTML page. Try to create a containing component, or a parent component with several children components using React.createElement() function.

Now let’s install Babel locally so that we don’t have to do all this stuff over and over again. Before installing Babel locally, we need to know what presets we need. To transpile JSX into stuff our browser understands, we need the following presets: 

@babel/plugin-syntax-jsx
@babel/plugin-transform-react-jsx
@babel/plugin-transform-react-display-name

We would also need the following presets. The last 3 are required for us to use all the cool features of ES6 and ES7, and the env preset is required for us to access const, arrow functions, spread operator, and a lot more!

env
es2015
es2016
es2017 

We will now install babel globally using the following command:

yarn add -g babel-cli

Now cd into your project and yarn init the project. This will create a package.json in our repository. Now we can add dependencies to your project. Now we can go ahead and add our babel preset dependencies using these commands:

yarn add babel-preset-env babel-preset-react

We will now be able to use JSX templates in our project! Move your entire project into a subdirectory called public, and write your JSX in src/app.js. Then enter this command in your terminal.

yarn babel src/app.js --out-file=public/scripts/app.js --presets=env,react

This command will take your JSX code from src/app and feed it to Babel, which will spit out the plain JavaScript output in the path provided to the --out-file flag. This plain JavaScript scripts file is imported in your HTML file and now you can directly use JSX to render components in the DOM.