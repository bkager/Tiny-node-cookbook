
# What's in Node

Before getting into details of Node, here's a quick overview of some of its components: 

* The JavaScript engine
* The Node bindings
* Libuv and the event loop
* The core Node modules (APIs)

## The JavaScript engine

All JavaScript runtime environments need a JavaScript engine, the software that actually interprets, compiles, and executes JavaScript code. There are multiple different JavaScript engines--for example, Chrome, Firefox, and Safari all use different ones. For the purpose of learning Node, you don't need to worry about the differences between engines or the details of how they work; just know that the engine is the software that translates JavaScript into code the computer can run. Node uses Google's V8 JavaScript engine, which is also part of Chrome.

&nbsp;

## The Node bindings

**XXX FILL IN XXX**

&nbsp;

## Libuv and the event loop

Libuv is a library that makes asynchronous operations possible in Node. Its main function is to provide the event loop. It's written in C. 

If you don't understand the event loop in JavaScript, you should learn it in the near future. This book assumes you have some familiarity with asynchronous JavaScript and how the event loop schedules operations. 

&nbsp;

## The core Node modules (APIs)

**XXX FILL IN XXX**

&nbsp;


## Summary 

* The Node runtime environment has various components.
* The only components you need to worry about right now are the core Node modules.
* You should understand the event loop before trying to write asynchronous code. 

&nbsp;

___

## Resources

**The event loop and asynchronous code**
https://youtu.be/fOdcuDigxfw?si=kRDpCqxwWFGkPusk
  * A good explanation of async code and the event loop.

**Libuv**
https://www.geeksforgeeks.org/libuv-in-node-js/
  * A detailed explanation of Libuv.
https://docs.libuv.org/en/v1.x/guide/basics.html
  * An explanation of libuv. 

### Up Next

Link to next recipe or section
