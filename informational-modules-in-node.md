# Modules in Node

You'll see "module" used to mean three different but related things in Node: 
1) The core Node modules
2) Your local modules
3) Third-party modules

## The Node core modules

The Node core modules together make up the Node standard library. They're included when you install Node, and they provide a lot of the functionality you'll use to create programs in Node. Each core module is a unit of code in the Node installation which contains functionality related to some general area: the `fs` module contains methods, functions, etc. relating to filesystem operations, the `http` module has functionality for receiving and sending http requests, etc. 

The core modules are APIs, and we can compare them to the Web APIs available to JavaScript in the browser. Like Web APIs, they're interfaces that allow you to interact with systems outside of Node.

The Node core modules are documented (along with other things) [here](https://nodejs.org/docs/latest/api/) on the Node website. We'll be looking at these docs a lot. 

The names of the core modules are: 
* assert
* buffer
* child_process
* **console**
* cluster
* **crypto**
* dgram
* dns
* events
* fs
* http
* http2
* https
* net
* os
* path
* perf_hooks
* **process**
* querystring
* readline
* repl
* stream
* string_decoder
* timers
* tls
* tty
* url
* util
* v8
* vm
* wasi
* worker
* zlib
  
Even though the core modules are a part of Node, you don't automatically have access to the functionality _in_ them. If you want to use a core module, you usually have to import it into the code you're writing before you can use anything inside it. A few "global" modules (the ones in bold in the list above) are always available and don't have to be imported. 

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
