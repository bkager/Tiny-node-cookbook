# The Tiny Node Cookbook
## Tasty, bite-sized recipes for learning Node.js

I love Node, but it can be hard to get started. The documentation in particular is not the most intuitive for new users, especially if JavaScript is your first programming language. I've found that a lot of existing tutorials echo this confusion--good at teaching bits and pieces, but not great at giving a top-down view of how everything fits together or prepping you to strike out on your own. 

This collection of Node recipes--tiny programs meant to demonstrate one or two features each--is intended to demonstrate the basic features of Node in a friendly, incremental way.

### Goals

* Demonstrate basic features of Node by building tiny programs
* Introduce new users to Node's docs
* Give new users enough basic knowledge to learn and build more on their own

### Who is this for?

This is aimed very much at beginners. If you're new to Node but have experience in other programming languages, you may find some of this, especially the early recipes, pretty basic. If JavaScript is your first programming language and you're just starting to lean Node, you should hopefully find that little background knowledge is assumed. I've tried to err on the side of overexplaining rather than underexplaining because there are already plenty of Node tutorials that do the opposite.

I am assuming that readers understand JavaScript fundamentals, including the structure of the language and how classes/inheritence work, basic HTML/CSS, are comfortable using a development environment like VSCode, and have some very basic familiarity with using a terminal and the command line.

In many ways, this for myself. I'd like to feel like I have a more comprehensive grasp of Node, and having to explain a topic is a great way to find where you're missing pieces. Here's the stuff I wish had been explained more clearly when I started.

Questions, suggestions, and corrections are very welcome. 

# Table of Contents

## Introduction

* Welcome to Node!
* How this cookbook is organized
* Keeping your own cookbook / notes
* Installing Node

## Node Basics: A Minimal Introduction to Some Important Bits

* What's in this section
* The Node environment vs. the browser environment
* Node on the command line: Basics

#### The Node shell
  * [Recipe: Random Number Generator](https://github.com/bkager/Node-cookbook/blob/main/recipe-random-number-generator.md)
    * Learn: Writing simple JavaScript code in the Node REPL
  
#### Node scripts
  * [Recipe: Greeter](https://github.com/bkager/Node-cookbook/blob/main/recipe-greeter.md)
    * Learn: Writing a simple program, JavaScript in the Node runtime environment  
  * [Recipe: Greeter + Names](https://github.com/bkager/Node-cookbook/blob/main/recipe-name-greeter.md)
    * Learn: The process module, passing arguments to a script
  * Recipe: Modules in Node
  * Recipe: Using someone else's module
  * Recipe: Publishing Greeter
  * Recipe: The console in Node
#### Node events: Basics
  * Node and event-driven architecture
  * The events module
  * The Node docs: our first module
  * Modules, classes, and interfaces as concepts
  * The EventEmitter class
#### Node filesystem operations: Basics
#### Node streams and buffers: Basics
#### Async in Node
#### HTTP requests in Node
   * HTTP requests/responses: the basics
#### Creating a server in Node: Basics
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
### Node events
### Node filesystem operations
### Node streams and buffers
### Creating a server
### Making HTTP requests as a client in Node

## Useful Resources

* [Useful Resources for Learning Node](https://github.com/bkager/Node-cookbook/blob/main/resources.md)

## License

The text of this book is licensed under a Creative Commons license (CC BY-NC-ND 4.0), which allows you to copy and redistribute the material in any format you like, but not create derivative works or use it for commerical purposes.

The code samples are licensed under an MIT license, which allows you to copy, redistribute, alter, and otherwise do what you like with the code for commercial or non-commercial purposes. 
