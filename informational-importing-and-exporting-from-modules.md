# Importing and Exporting from Modules

Keeping your code modular is great: it's much easier to maintain and understand than just leaving your entire program into one file. However, if you break your program up into ten smaller modules instead of one big file, it does mean that code in one file will often need to consume code in another file. Say you store a function called sayHello() in module1 and want to call it from module2. You have to expose sayHello() to other code by exporting it from module1, and in order to use it in module2 specifically, you have to import it there.

There are two types of syntax for importing and exporting in modern JavaScript: ES6 modules, which use `import` and `export` statements, and CommonJS modules, which use `exports` and `require()`. Node supports both types. CommonJS modules were the original system used by Node, and if you run across older tutorials, they're likely to only discuss CommonJS. 

## CommonJS module imports/exports

Say we have a folder containing two files, 'duck-functions.js' and 'index.js'. We have one function in `duck-functions.js` that we want to export so we can use it in `index.js`. 

```
//In duck-functions.js:

function sayQuack () {
  console.log("Quack quack quack!")
}

module.exports.sayQuack = sayQuack;
```

Node automatically creates a `module` object for each module of code. The `exports` object exists automatically on the module object. `Exports` is where we're going to put anything we want to make available to other files. 

![Visualization showing the module object representing the module, and some of the object's contents, including the .exports object](https://github.com/user-attachments/assets/3ba7d78f-d5f5-4944-aa86-27bb29056c72)


We've added a property, `sayQuack`, to the exports object, and given it the value of the function definition of `sayQuack`. Module.exports is exposed to other files that want to use things we've put in it. In fact, module.exports is the value of our module, as far as other files are concerned. We can import the `sayQuack` function into our index.js file and invoke it like this:

```
//In index.js:

const duckFunctions = require('./duck-functions.js');

duckFunctions.sayQuack() //Prints "Quack quack quack!"
```

We're importing the module.exports object to index.js, saving it to the variable duckFunctions, and then invoking the function we saved in it as .sayQuack(). I've demonstrated this syntax first because I think it's the easiest to see what's happening, but there are several ways to do this.

### Syntax #1


```
//In duck-functions.js:

function sayQuack () {
  console.log("Quack quack quack!")
}

module.exports.sayQuack = sayQuack;
```

```
//In index.js:

const duckFunctions = require('./duck-functions.js');

duckFunctions.sayQuack() //Prints "Quack quack quack!
```







## ES6 module imports/exports


## Summary 
* Node supports both CommonJS and ES6 modules.
* 

&nbsp;

___

## Bonus recipes

* Bonus recipes in bullet points here

 &nbsp;

## Resources

### Up Next

Link to next recipe or section
