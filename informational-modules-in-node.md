# Modules in Node

You'll see "module" used to mean three different but related things in Node: 
1) The core Node modules
2) Your local modules
3) Third-party modules

## The Node core modules




## Your local modules

When you build a JavaScript project of any real complexity, you'll want to split your code up into multiple files. Each of your separate code files is also a "module". Keeping your code modular makes it easier to build, maintain, and understand. However, to get these files to work together, you have to export code from the file where it lives and import it into another where you want to make use of it.

&nbsp;

### Third party modules

Third party modules are code packages published by other people for you to use in your own code. These have to be not only imported into your code files, but downloaded and installed. We'll cover finding and installing 3rd party modules later as well.

### Modules

All three types of modules are, fundamentally, just chunks of code, whether written by you or by other people. To allow code in one file to make use of code in another file, we have to import/export it, which we'll cover in the next section.
&nbsp;

## Summary 
* The Node core modules are APIs which give you access to functionality beyond the core JavaScript language, like making http requests and accessing the file system on your computer.
* Local modules are code which you write. Keeping your code organized into many small modules instead of one big file is easier.
* 3rd party modules are code written by other people.
* You have to export code from modules where it is written and import it into other modules if you want to use it there. 

&nbsp;

___

## Resources

### Up Next

Link to next recipe or section
