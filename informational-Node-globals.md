# The Node globals

[As mentioned](https://github.com/bkager/Tiny-node-cookbook/blob/main/informational-modules-in-node.md), most of Node's core modules need to be imported into a file before you can use them. However, a few are "global" modules which are always available without importing. There is also a small number of objects, classes, and methods which are available globally even though the larger modules they belong to are not. These are things you use often enough that importing them every time would be annoying or where importing their entire module to use them would be a waste. 

A familiar example is the `console` object, which you can use in any file without explicitly importing it. 

You can see the full list of globals in the Node docs [here](https://nodejs.org/docs/latest/api/globals.html).

## A few example globals

* console
  * The good old `console` object.
* process
  * The `process` object contains properties and methods having to do with the running Node process itself. You'll use properties like `process.env`, which is an object containing data about the user environment (like the current directory), and `process.argv`, which is an array containing any arguments passed to Node on the command line.
* Event and EventTarget
  * Two classes that are important to Node's event-driven architecture. 
* `fetch()`
  * An implementation of the `fetch()` function, which is also found in browsers.
* `setInterval()` and `setTimeout()`
  * Two timer functions that you can use to schedule functions to execute after a delay.  

## Pseudo globals

There are also a few things that look like globals but aren't. The list is [here](https://nodejs.org/docs/latest/api/globals.html#global-objects) and includes variables like `__filename` (which returns the current module's file name). They feel like globals because they're always available to use without import, but they actually exist in the scope of a particular module, not in the global scope. This makes sense: every module will have a separate value for `__filename`, after all. 


## Summary 
* A handful of common and useful Node objects don't need to be imported into a file to use them. 

___

## Resources

### Up Next

Link to next recipe or section

