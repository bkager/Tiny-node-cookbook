# The Tiny Node Cookbook
## Tasty, bite-sized recipes for learning Node.js

Node is a popular way to write JavaScript that runs outside of the web browser. I love Node, but it can be hard to get started, especially if JavaScript is your first programming language. The documentation, in particular, is not the most intuitive for new users. I've found that a lot of existing tutorials echo this confusion--good at teaching bits and pieces, but not great at giving a top-down view of how everything fits together or prepping you to strike out on your own. 

This collection of Node recipes--tiny programs meant to demonstrate one or two features each--is intended to help you learn the basic features of Node in a friendly, incremental way.

The book is currently in a very partial first draft. 

### Goals

* Demonstrate basic features of Node by building tiny programs
* Introduce new users to Node's docs
* Give new users enough basic knowledge to learn and build more on their own

### Who is this for?

This is aimed at beginners to Node, but not beginners to JavaScript. If you're new to Node but have experience in other programming languages, you may find some of this, especially the early recipes, pretty basic. If JavaScript is your first programming language and you're just starting to learn Node, your should hopefully find that little background knowledge is assumed. I've tried to err on the side of overexplaining concepts like servers, http requests, and interfaces rather than underexplaining, because there are already plenty of Node tutorials aimed at more experienced developers. In my own path to learning programming, I've found that relatively few things at the beginner level are actually *hard*, but plenty of things seem hard because explanations assume background knowledge you're missing.

I am assuming that readers understand JavaScript fundamentals like functions, variables, operators, and classes; plus a basic grasp of inheritence, asynchronous programming, and some of the Web APIs available in the browser, even if you feel like you need some brushing up on those concepts. You should know some very basic HTML/CSS, be comfortable using an IDE like VSCode, and have some basic familiarity with using a terminal and the command line. If you're not quite sure if you're ready for Node, I recommend jumping in and working until you find you need to go off and learn some concept. I try to be very clear about marking what background knowledge you need. 

In many ways, this for myself. Here's the stuff I wish had been explained more clearly when I started.

Questions, suggestions, and corrections are very welcome! Open an issue on Github or contact me at britta.ager at gmail. 

# Table of Contents

## Introduction

* [Introduction](https://github.com/bkager/Node-cookbook/blob/main/introduction.md)
  * Welcome to Node!
  * What Node is and does
  * How this cookbook is organized
  * Keeping your own cookbook / notes
  * Installing Node

## Node Basics: A Minimal Introduction to Some Important Bits

### Some preliminary info
* [The Node environment vs. the browser environment](https://github.com/bkager/Node-cookbook/blob/main/informational-node-vs-browser.md)
* [What's in Node](https://github.com/bkager/Node-cookbook/blob/main/informational-whats-in-node-basics-section.md)
  * The V8 Engine, libuv, and bindings
  * The core Node modules (APIs)
* [Node modules](https://github.com/bkager/Node-cookbook/blob/main/informational-modules-in-node.md)
  * The core modules, local modules, and 3rd party modules
* [Importing and exporting from modules](https://github.com/bkager/Node-cookbook/blob/main/informational-importing-and-exporting-from-modules.md)
* [Node globals * ](https://github.com/bkager/Node-cookbook/blob/main/informational-Node-globals.md)
  * The handful of modules and other objects that are always available. 

### The Node REPL
  * The Node REPL: Introduction
  * [Recipe: Random Number Generator](https://github.com/bkager/Node-cookbook/blob/main/recipe-random-number-generator.md)
    * Learn: Writing simple JavaScript code in the Node REPL
  
### Simple Node programs
  * [Recipe: Greeter * ](https://github.com/bkager/Node-cookbook/blob/main/recipe-greeter.md)
    * Learn: Writing a simple program, JavaScript in the Node runtime environment
  * [Recipe: Greeter + Names * ](https://github.com/bkager/Node-cookbook/blob/main/recipe-name-greeter.md)
    * Learn: The process module, passing arguments to a program
  * Recipe: Goodbyer
    * The console in Node. Node's I/O. Piping it to another program. 

### IDEs
  * VSCode
    * Switching over to using a modern coding environment

### Node modules
  * Node core modules
  * Recipe: Import the XXX module
  * Local modules
  * Recipe: Import and export your own modules
  * Third party modules
  * Recipe: Import the XXX module
    
### NPM
  * Npm: An introduction to Node's package manager
    * Exploring npm
  * Recipe:
    * Install, update, and remove a package; basic npm commands
  * Recipe: Publishing Greeter
    * Publish a package to npm, install it, use it, and unpublish it 
    
### The Node docs
  * Reading the Node docs website
  * Creating your own docs
  * The core modules; APIs, classes, and interfaces as concepts
  * Recipe: Examining the console or process module
    * Practice: Making use of the docs 

### Node events: Basics
  * Node and event-driven architecture
  * The events module
    * The Node docs: our first module in depth
  * The EventEmitter class
  * Recipe: Logging/responding to some events
### Async in Node
  * Handling asynchronous operations
### Node filesystem operations: Basics
  * Node fs and path modules
### Node streams and buffers: Basics
  * Node buffer and stream modules
### HTTP requests in Node
   * HTTP requests/responses: the basics
### Creating a server in Node: Basics
   * [Basic Node Servers intro](https://github.com/bkager/Node-cookbook/blob/main/discussion-intro-to-servers.md)
     * What clients and servers are, the basics of http requests, and why Node is often used to create servers.
   * [Recipe: Do-nothing Server](https://github.com/bkager/Node-cookbook/blob/main/recipe-do-nothing-server.md)
      * Create a server and set it to listen on a port   
   * [Recipe: Cat Server 1](https://github.com/bkager/Node-cookbook/blob/main/recipe-cat-server-1.md)
      * Inspecting an incoming request
   * [Recipe: Cat Server 1 alternate syntax](https://github.com/bkager/Node-cookbook/blob/main/recipe-cat-server-1-alternate-syntax.md)
      * Requests as events, the request handler as an event handler, and an alternate way to set up a server
   * [Recipe: Cat Server 2](https://github.com/bkager/Node-cookbook/blob/main/recipe-cat-server-2.md)
      * Sending back a response
   * Recipe: Cat Server 3
      * Handling requests to different paths
   * Recipe: Cat Server 4
      * Request bodies
   * Recipes to figure out
      * POST requests
      * DELETE requests
      * PUT requests
      * Returning data

## Beyond the Basics

### Node on the command line
 * More complex scripting
### Node events
### Node filesystem operations
### Node streams and buffers
### Creating a server
### Making HTTP requests as a client in Node
### Authentication
### Debugging
### Testing
### Deploying


## Useful Resources

* [Useful Resources for Learning Node](https://github.com/bkager/Node-cookbook/blob/main/resources.md)

## License

The text of this book is licensed under a Creative Commons license (CC BY-NC-ND 4.0), which allows you to copy and redistribute the material in any format you like, but not create derivative works or use it for commerical purposes.

The code samples are licensed under an MIT license, which allows you to copy, redistribute, alter, and otherwise do what you like with the code for commercial or non-commercial purposes. 
