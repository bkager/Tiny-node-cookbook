# Greeter + Names

````
// This is a simple JavaScript program that accepts a name as an argument and outputs a greeting to the named person. 

const greetings = ["Hello", "Hi", "Howdy", "Welcome", "Hiya"]; 

const name = process.argv[2]

let length = greetings.length;

let randomNum = Math.floor(Math.random() * length);

console.log(`${greetings[randomNum]}, ${name}!`);
````
___

This program will show you how to add an argument when you invoke your Autogreeter program.

**Understand**
* The Node process module
___
**The Process Module**

If you followed recipe XXXNUMBER, you created a program that outputs random greetings to the command line when you run it in Node. It's a very limited program, though, and can't respond to input. You just invoke it, it does its thing, you get some random output from a pre-programmed list of possibilities. We'd like to be able to pass arguments to a program  that it can then use in its code, just as we can pass arguments into functions. In this case, we could pass in a name and have the program return a personalized greeting. 

![Screenshot of a terminal. The command "node name-greeter.js" is entered and the output is "Welcome, Britta!"](https://github.com/bkager/Node-cookbook/assets/68086185/2427dc11-d4a4-4ff2-ae69-1cb07c6a27ee)


To give the code inside your script file access to a name you type on the command line, you need the Node [process module](https://nodejs.org/api/process.html#processconfig). XXX:LINK TO ANY PREVIOUS DISCUSSION OF CORE MODULES. The process module is a core Node module--it's something built into the basic Node program. It's global, meaning that unlike some Node modules, you don't have to explictly import it into your code when you want to use it. As long as your code is running in a Node environment, it will always have access to the stuff in `process`. 

The process module contains one thing, the process object. This in turn contains a variety of methods and properties having to do with the current Node.js process. For example, the process.env property has the value of an object which contains variables describing the user environment. You can view it by starting the Node REPL and typing `console.log(process.env)`, which will print a an object to the console with properties like `USER` (your username) and `HOME` (the path to your home directory).

![Screenshot of above instructions and their output](https://github.com/bkager/Node-cookbook/assets/68086185/99c55486-25bb-4648-be67-a60765a5efb2)

You don't need to worry about process.env right now, but it's a good sample of the sort of stuff the process module gives you access to--information about the Node process that is currently running and the environment it's running in on your computer. 

___
**process.argv**

The one piece of the process object that we'll worry about right now is the .argv property. Proces.argv holds an array containing the command-line arguments passed in when a Node process is launched. When you tell Node to execute a script like greeter.js, XXX: CHANGE NAME, if you type anything after the command `node greeter.js`, Node will save that extra input in the process.argv array. 

To try this out, exit the Node REPL and create a new testfile called testfile.js. In it, enter `console.log(process.argv)`, and save it. From the command line, tell Node to run this program: 

![Screenshot of terminal. Command entered: "node testfile.js". Output described below.](https://github.com/bkager/Node-cookbook/assets/68086185/962480c3-08e9-48a6-9e2c-f00f878e7735)

Your program prints out the process.arv array. This array always contains at least one value, which is the path to the Node installation on your machine. If you console.log process.argv from inside the Node REPL, it will return an array containing just this. If you console.log process.env from inside a program you've written and run with node, the second value will be the path to the program, which you can see it outputting here from my test file. 

Here's where process.argv gets fun. If we add any other values on the command line when we run our program, those values will also be saved in process.argv. Run testfile.js again and add a few random words after the `node testfile.js` command:

![Screenshot of terminal. Command entered: "node testfile.js parrot 'beach ball' shiny". Output described below.](https://github.com/bkager/Node-cookbook/assets/68086185/e5c82eba-baad-43d2-9972-8d012a5e286c)

Our process.argv array now contains the three new arguments that I added when running the program. We've logged these values from inside our program, meaning that they're available inside our code thanks to the process.argv array. We can grab those values out of process.argv and do whatever we want with them. 

To try this out, create a new file called `name-greeter.js` and enter the code at the top of the page in it. Save it, and from the command line, tell Node to run your program, adding a name after the command: 

![Screenshot of above instructions. Output is: "Welcome, Britta!"](https://github.com/bkager/Node-cookbook/assets/68086185/2fae619a-45ee-4f1e-90af-b74d19cfcb67)

Neat; we've now made our little JavaScript program accept input. If we wanted to complicate it a bit, we could add some logic to the program so we get different output depending on the name we input: 

````
const greetings = ["Hello", "Hi", "Howdy", "Welcome", "Hiya"]; 

const name = process.argv[2]

let length = greetings.length;

let randomNum = Math.floor(Math.random() * length);

if (name === "Dave") {
	console.log("You again?");
} else {
	console.log(`${greetings[randomNum]}, ${name}!`);
}
````

![Screenshot of terminal. Command: "node name-greeter.js Britta". Output: "Hiya, Britta!". Command: "node name-greeter.js Dave. Output: "You again?"](https://github.com/bkager/Node-cookbook/assets/68086185/db38099e-63a9-4b14-a16d-23af41b913d3)

So there you have it: a way to pass an argument into your script, and a basic understanding of the process module. 
____

### Bonus Recipes

* Create a program that accepts a number argument and outputs the number times two.
* Create a program that accepts a simple description of the weather ("rainy", "sunny", etc.) and outputs some advice on what to wear today based on it.
* Create a program that accepts any number of command line arguments and saves them as values in an object with numbers as keys.





Is the process object 
Discuss Node startup and how a process object is created
Define 'the current Node process'
