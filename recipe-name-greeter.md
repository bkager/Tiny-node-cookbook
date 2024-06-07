# Name Greeter

````
// This is a simple JavaScript program that accepts a name as an argument and outputs a greeting to the named person. 

const greetings = ["Hello", "Hi", "Howdy", "Welcome", "Hiya"]; 

let length = greetings.length;

let randomNum = Math.floor(Math.random() * length);

console.log(greetings[randomNum]);
````

___

This program will show you how to add an argument when you invoke your Autogreeter program.

**Understand**
* The Node process module
___

If you followed recipe XXXNUMBER, you created a program that outputs random greetings to the command line when you run it in Node. It's a very limited program, though, and can't respond to input. You just invoke it, it does its thing, you get some random output from a pre-programmed list of possibilities. We'd like to be able to pass a program arguments that it can then use in its code, just as we can pass arguments into functions. In this case, we could pass in a name and have the program return a personalized greeting. 

![Screenshot of a terminal. The command "node name-greeter.js" is entered and the output is "Welcome, Britta!"](https://github.com/bkager/Node-cookbook/assets/68086185/2427dc11-d4a4-4ff2-ae69-1cb07c6a27ee)


To give the code inside your script file access to a name you type on the command line, you need the Node [process module](https://nodejs.org/api/process.html#processconfig). XXX:LINK TO ANY PREVIOUS DISCUSSION OF CORE MODULES. The process module is a core Node module--it's something built into the basic Node program. It's global, meaning that unlike some Node modules, you don't have to explictly import it into your code when you want to use it. As long as your code is running in a Node environment, it will always have access to the stuff in `process`. 

The process module contains one thing, the `process` object, which contains a variety of methods and properties having to do with the current Node.js process. For example, the process.config property's value is an object holding configuration settings. XXX: CONSOLE.LOG THIS STUFF FROM INSIDE NODE. XXX: ADD A METHOD.

The only piece of the process object to worry about right now is process.argv. 

____
Do events count as a separate thing?
What's the technical definition of a script?
Is the process object 
Discuss Node startup and how a process object is created
Define 'the current Node process'
