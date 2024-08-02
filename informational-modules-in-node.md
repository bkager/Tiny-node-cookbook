# Modules in Node

You'll see "module" used to mean three different but related things in Node: 
1) The core Node modules
2) Your local modules
3) Third-party modules

All three types of modules are files containing code.

## The Node core modules

As discussed in the [last section](https://github.com/bkager/Node-cookbook/blob/main/informational-whats-in-node-basics-section.md), the Node core modules are APIs which contain the main tools that Node gives you. They're a key part of the Node installation. However, even though the core modules are downloaded when you install Node, your code doesn't automatically have access to the functionality _in_ them. If you want to use the tools in a core module, you usually have to import it into your code first. This helps keep the packages of code you're writing small--your application only requires specific parts of Node instead of all of it. **XXX CHECK THIS; TALK ABOUT MORE XXX** 

A few "global" modules are always available and don't have to be imported. See the [Node globals](https://github.com/bkager/Node-cookbook/blob/main/informational-Node-globals.md) page later in this section for more on this.


## Your local modules

When you build a JavaScript project of any real complexity, you'll want to split your code up into multiple files. Each of your separate code files is also a "module". Keeping your code modular makes it easier to build, maintain, and understand. However, to get these files to work together, you have to export code from some files and import it into others. 

## Third party modules

Third party modules are code packages published by other people for you to use in your own code. These have to be not only imported into your code files, but downloaded and installed. We'll cover finding and installing 3rd party modules later as well.

### Modules

All three types of modules are, fundamentally, just chunks of code, whether written by you or by other people. To use code from one file in another file, you have to export it from the first file and import it into the second. The [next unit](https://github.com/bkager/Node-cookbook/blob/main/informational-importing-and-exporting-from-modules.md) discusses how to do this. 

## Summary 
* The Node core modules are APIs which give you access to functionality beyond the core JavaScript language, like making http requests and accessing the file system on your computer.
* Local modules are code which you write. Keeping your code organized into many small modules instead of one big file is easier.
* 3rd party modules are code written by other people.
* You have to export code from modules where it is written and import it into other modules if you want to use it there. 

&nbsp;

___

## Resources

### Up Next

[Importing and exporting from modules](https://github.com/bkager/Node-cookbook/blob/main/informational-importing-and-exporting-from-modules.md)
