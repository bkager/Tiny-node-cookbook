
# What's in Node

Before getting into details of Node, here's a quick overview of some of its components: 

* The JavaScript engine
* The Node bindings
* Libuv and the event loop
* Other dependencies
* The core Node modules (APIs)

&nbsp;

## Node Uses

The following components are dependencies that Node uses under the hood. You don't need to worry about how they work; Node handles all of these for you. 

### The JavaScript engine

All JavaScript runtime environments need a JavaScript engine, the software that actually interprets, compiles, and executes JavaScript code. There are multiple different JavaScript engines--Chrome, Firefox, and Safari, for example, all use different ones. You don't need to worry about the differences between engines or the details of how they work to learn Node. Just know that the engine is the software that translates JavaScript into code the computer can run, and it works under the hood without your input. Node uses Google's popular V8 JavaScript engine, which was developed for Chrome.


### The Node C/C++ bindings

The Node C/C++ bindings translate between JavaScript code and C/C++ code. This is necessary to allow Node to do things like interact with the filesystem on a computer. 


### Libuv and the event loop

Libuv (pronounced "lib-you-vee") is a library that makes asynchronous I/O operations possible in Node. Its main function in Node is to provide the event loop. It's written in C. 

If you don't understand the event loop in JavaScript, you should learn it before getting too deep into Node, because asynchronicity is very important for Node applications. This book assumes you have some familiarity with asynchronous JavaScript and how the event loop schedules operations. 

### Other dependencies

Node also relies on a few other dependencies:

c-ares: A library for asynchronously resolving DNS queries.
http-parser: A parser for HTTP requests/responses written in C.
OpenSSL: Open-source cryptographic packae that helps encrypt network communications.
zlib: A library used for data compression.

Again, these are all components that just work without you needing to worry about them! If you're curious, though, there are some links in "Resources" at the bottom of the page with more details.

&nbsp;

## Node Provides

### The core Node modules (APIs)

The Node core modules are APIs, tools provided by Node for you to use in writing your own code. Like Web APIs in the browser, the Node core modules give you access to systems outside of Node that Node and functionality that isn't part of the JavaScript language itself. Together, they're known as the Node standard library, and they make up the majority of what you'll deliberately use from Node (as opposed to the parts, like the V8 engine, which work under the hood without your input).

Each core module is a collection of functionality related to some general area: the `fs` module contains methods and properties relating to filesystem operations, the `http` module contains methods and properties for receiving and sending http requests, and so on.

The core modules are documented [here](https://nodejs.org/docs/latest/api/) on the Node website. 

The names of the core modules are: 
* assert
* buffer
* child_process
* console
* cluster
* crypto
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
* process
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

The bulk of this book will be detailed investigations of what you can do with these modules. 

&nbsp;

## Node is Accompanied By

### NPM

When you install Node, it also installs NPM, a package manager which helps you find, install, and manage packages of code that you want to use in your own projects. NPM is really handy and will be discussed in [its own section](https://github.com/bkager/Node-cookbook?tab=readme-ov-file#npm).

&nbsp;

## Summary 

* The Node runtime environment has various components.
* The only components you need to worry about right now are the core Node modules, which this book will cover extensively.
* You should understand the event loop before trying to write asynchronous code. 

&nbsp;

___

## Resources

**The event loop and asynchronous code**
https://youtu.be/fOdcuDigxfw?si=kRDpCqxwWFGkPusk
  * A good explanation of async code and the event loop.

**Libuv**
https://youtu.be/kCJ3PFU8Ke8?si=UhYiyq9w4CsmREPk
  * Intro to libuv
https://www.geeksforgeeks.org/libuv-in-node-js/
  * A detailed explanation of Libuv.
https://docs.libuv.org/en/v1.x/guide/basics.html
  * An explanation of libuv. 

### Up Next

Link to next recipe or section
