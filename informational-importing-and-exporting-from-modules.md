# Importing and Exporting from Modules

Keeping your code modular is great: it's much easier to maintain and understand than just leaving your entire program in one file. However, if you break your program up into ten smaller modules instead of one big file, it does mean that code in one file will often need to consume code in another file. Say you store a function called sayHello() in module1 and want to call it from module2. You have to expose sayHello() to other code by exporting it from module1. Then you have to import it to module2 to make it specifically available to code there. 

There are two types of syntax for importing and exporting in modern JavaScript: the syntax you use with ES6 (ECMAScript) modules, which use `import` and `export` statements, and the kind you use with CommonJS modules, which use `module.exports` and `require()`. Node supports both types. CommonJS modules were the original system used by Node, and if you run across older tutorials, they're likely to only discuss CommonJS. 

## Which type of modules to use?

ES6 modules are newer and are, per [the official JavaScript specification](https://tc39.es/ecma262/#sec-modules), the standard format for JavaScript modules. They offer performance improvements over CommonJS modules. In particular, ES6 modules are loaded asynchronously, while CommonJS modules load synchronously and thus block other code execution. Node now supports ES6 modules but still treats CommonJS as the default—if you don't explictly set up modules as described in the next section, Node will treat your modules as CommonJS. 

ES6 modules can import CommonJS modules with no problem using the `import` syntax described below. CommonJS modules, however, cannot import ES6 modules the way they import other CommonJS modules. See the special syntax you have to use below. 

Thus if you use ES6 modules you have to do a little extra setup but then don't have to worry about whether modules you import are ES6 or CommonJS; but your code will be less compatible with older Node versions and code using CommonJS unless you use a transpiler to translate it from ES6 syntax into ES5 syntax. If you use CommonJS modules you'll be using the Node default and your code will be compatible with older Node programs, but you'll have to pay attention to what types of modules you import and change your import syntax when importing ES6 modules. 

## Module set up

In order to import/export from a module, you have to tell Node which type of modules you're using, CommonJS or ES6. There are two ways to do this: 
  * You can set the file extension of each module to .cjs for CommonJS or .mjs for ES6.
  * You can add the following to your `package.json` file:
```
//For CommonJS:
"type": "commonjs"
//For ES6:
"type": "module"
```
If you use the file extensions, don't forget you'll have to use the right extension where you use the filename in import statement. 

## CommonJS module imports/exports

Say we have a folder containing two files, 'duck-functions.js' and 'index.js'. We have one function in `duck-functions.js` that we want to export so we can use it in `index.js`. 

```
//In duck-functions.js:

function sayQuack () {
  console.log("Quack quack quack!")
}

module.exports.sayQuack = sayQuack;
```

In Node, each file is considered a separate module, and Node automatically creates a `module` object for each file. The `exports` object exists automatically on the module object. This `module.exports` object is where we're going to put anything we want to export. 

![Visualization showing the module object representing the module, and some of the object's contents, including the .exports object](https://github.com/user-attachments/assets/3ba7d78f-d5f5-4944-aa86-27bb29056c72)


We've added a property, `sayQuack`, to the exports object, and given it the value of the function definition of `sayQuack`. Module.exports is exposed to other files that want to use things we've put in it. In fact, module.exports _is_ the value of our module, as far as other files are concerned. We can import the `sayQuack` function into our index.js file and invoke it like this:

```
//In index.js:

const duckFunctions = require('./duck-functions.js');

duckFunctions.sayQuack() //Prints "Quack quack quack!"
```

We're importing the module.exports object to index.js, saving it to the variable duckFunctions, and then invoking the function we saved in it as .sayQuack(). I've demonstrated this syntax first because I think it's the easiest to see what's happening, but there are several ways to do this.

### Syntax #1: Add variables and functions to the exports object

This is what you've seen already, but with two things to export. You can add multiple variables and function definitions to the exports object.

```
//In duck-functions.cjs:

function sayQuack () {
  console.log("Quack quack quack!")
}

const duckName = "Herbert";

module.exports.sayQuack = sayQuack;
module.exports.duckName = duckName;
```

```
//In index.cjs:

const duckFunctions = require('./duck-functions.js');

duckFunctions.sayQuack(); //Prints "Quack quack quack!
console.log(duckFunctions.duckName); //Prints "Herbert"

```
### Syntax #2: The same, with destructuring

You can tidy up the syntax above using destructuring: 

```
//In duck-functions.cjs:

function sayQuack () {
  console.log("Quack quack quack!");
}

const duckName = "Herbert";

module.exports = {sayQuack, duckName};
```

```
//In index.cjs:

const {sayQuack, duckName} = require('./duck-functions.cjs')

sayQuack(); //Prints "Quack quack quack!
console.log(duckName); //Prints "Herbert"
```

### Syntax #3: A default export

If you're only exporting one thing, you can simply set module.exports equal to it: 

```
//In duck-functions.cjs:

function sayQuack () {
  console.log("Quack quack quack!")
}

module.exports = sayQuack;
```

```
//In index.cjs:

const sayQuack = require('./duck-functions.cjs');

sayQuack();
```
### Importing ES6 modules into CommonJs modules with a dynamic import

Remember: the import methods shown above only work to import into a CommonJS module FROM another CommonJS module. To import into CommonJS from an ES6 module, you need to use the following syntax: 

```
```

## ES6 module imports/exports

### Syntax #1: Named exports

With ES6 modules, you use this syntax, putting the `export` keyword in front of the items to export: 
```
//In duck-functions.mjs

export function sayQuack () {
  console.log("Quack quack quack!")
}

export const duckName = "Herbert";
```

```
//In index.mjs

import {sayQuack, duckName} from './duck-functions.mjs';

sayQuack(); //Prints "Quack quack quack!"
console.log(duckName); //Prints "Herbert"
```

You can also collect all your exports at the end of the file like this: 

```
function sayQuack () {
  console.log("Quack quack quack!")
}

const duckName = "Herbert"; 

export {sayQuack, duckName};
```

### Renaming imports

You can rename items when you export or import them: 
```
//In duck-functions.mjs
export {sayQuack as makeNoise}
//In index.mjs
import {makeNoise} from './duck-functions.mjs';
```
```
//In duck-functions.mjs
export {sayQuack}
//In index.mjs
import {sayQuack as makeNoise} from './duck-functions.mjs';
```

### Syntax #2: Default exports

If you want a single default export for the module, add the `default` keyword when exporting. You can also export other, named exports from the same file. You can only have one default export, which you import/export without using the destructuring bracket notation. You can have as many named imports as you want, and they still need brackets.

```
//In duck-functions.mjs

export default function sayQuack () {
  console.log("Quack quack quack!")

export const duckName = "Herbert";

```

```
//In index.mjs

import sayQuack, {duckName} from './duck-functions.mjs';

sayQuack(); //Prints "Quack quack quack!"
console.log(duckName); //Prints "Herbert"
```
You can rename a default import without specifying what you're importing (there's only one default, so Node knows what you're referring to in this import no matter what you call it):
```
import makeNoise from './duck-functions.mjs';

makeNoise(); //Prints "Quack quack quack!"
```

### Import all and dot notation

You can also import all available exports from a module into one object, and then access them on it with dot notation: 
```
//In duck-functions.mjs

export function sayQuack () {
  console.log("Quack quack quack!")
}

export const duckName = "Herbert"; 
```
```
//In index.mjs

import * as duckStuff from './duck-functions.mjs';

duckStuff.sayQuack(); //Prints "Quack quack quack!"
console.log(duckStuff.duckName); //Prints "Herbert"

```
## Summary 
* Node supports both CommonJS and ES6 modules.
* You have to tell Node which type of module you're using with file extensions or a "type" property in package.json.
* There are multiple syntaxes you can use with both module types.

&nbsp;

___

## Resources

[Kingsley Ubah, CommonJS vs. ES modules in Node.js](https://blog.logrocket.com/commonjs-vs-es-modules-node-js/) 
[Rajkumar Gaur, CommonJS and ESM modules interoperability in NodeJS](https://sliceofdev.com/posts/commonjs-and-esm-modules-interoperability-in-nodejs)
[Rahul Jindal, ES6 imports vs CommonJS imports](https://medium.com/@rahul.jindal57/es6-imports-vs-commonjs-imports-8e9b66aa04bd#:~:text=CommonJS%20Import%20Syntax%3A&text=const%20defaultModule%20%3D%20require('module,is%20used%20to%20import%20modules.)
[Digital Ocean tutorial on ES6 modules](https://www.digitalocean.com/community/tutorials/js-modules-es6)

### Up Next

Link to next recipe or section
