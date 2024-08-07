# Greeter

```
const greetings = ["Hello", "Hi", "Howdy", "Welcome", "Hiya"]; 

let length = greetings.length;

let randomNum = Math.floor(Math.random() * length);

console.log(greetings[randomNum]);


```

This minimal program will show you how to write JavaScript in a file from the command line, and then execute the code in that file in Node from the command line. 

## Goals
* Write a simple JavaScript program in a file
* Run your file in Node
* Understand that Node is just a different environment for JavaScript
  
## You should already understand
* Have very basic comfort with using a terminal and simple command line operations
* Have a command line text editor


# Instructions

Open a terminal program and navigate to a folder where you want to save the program you're going to write. For example, I'll put mine on my desktop, so I navigate to ~/Desktop. 

![screenshot of Desktop folder in the terminal](https://github.com/bkager/Node-cookbook/assets/68086185/22b0d6c6-acb6-4165-b483-3c353db71e82)

You're going to create a file and write in it from the command line. For this, you'll need to have a command-line text editor program. If you've worked on the command line much before, you probably already have a favorite. If you haven't, you probably have one called nano already installed on your computer. Type `nano` at the command prompt to open the nano editor. Try it out, then type CTRL+X to exit your test file. You should be back at the command prompt so we can create our actual JavaScript program. 

> Side note: Nano uses commands that may not feel intuitive. They're easy to get used to, but there are many other command line text editors which you may prefer. [micro](https://micro-editor.github.io/), for instance, uses the same commands for cut, paste, save, etc. that most modern word processors like MS Word use.

To create your program file, enter `nano greeter.js` at the command prompt. This will create a new file in your current directory called 'greeter.js' and open it in nano for editing. JavaScript files use the `.js` file extension.

Add the text of the recipe above to your file. 

Notice that this is just standard JavaScript code. In the last recipe, you wrote JavaScript in the Node REPL. Here, you're writing it in a reusable file that you'll save and execute from the command line as many times as you want.

Save your file and exit (in nano, CTRL+X).

From the command line, enter `node greeter.js`. In the last recipe, you entered just `node` to open the Node REPL and work in it. Entering `node <file path>` will instead take the named file and run the code inside of it in the Node runtime environment. Note that because we're already in the same folder on our system that holds the file, the path to it is just the filename `greeter.js`, but if we wanted to run a file stored in a different directory, we would need to use a relative file path that told Node where to find it relative to our current working directory.

Since Node is a JavaScript runtime environment, it has everything necessary to run JavaScript code, and you've written JavaScript in your file and given it the `.js` extension, so Node should read your code and run it, line by line.

The output of the program appears on the command line: a random greeting!

Run it a few more times and get different outputs from the random greeting generator. 

There's nothing special about command line text editors except convenience--you're already in a terminal, they're in a terminal, how handy. But you could just as well open your JavaScript file in TextEdit or some other editing program, write in it there, save it, and go back to the command line to run it in Node. 

Notice that this program doesn't take any input--you can't, for example, give it a person's name and have it greet them specifically. We'll add that in the next recipe, and look at the Node process module at the same time. 


## Summary 
* JavaScript code is just text. You can write it in any text editor.
* You can save your code in a text file and then run the file as many times as you want.
* Node, as a JavaScript runtime environment, is a program that can read and execute a file of JavaScript code.
* Name JavaScript files with a `.js` file extension.

&nbsp;

___

## Bonus recipes

* Create a new file in the same directory and have it output random insults instead. Run it from the command line.
* Create a program that outputs the date and time.

 &nbsp;


## Resources
 
### Up Next

Link to next recipe or section
