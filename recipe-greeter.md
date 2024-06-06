# Autogreeter

````

// This is a simple JavaScript program that outputs a greeting. 

const greetings = ["Hello", "Hi", "Howdy", "Welcome", "Hiya"]; 

let length = greetings.length;

let randomNum = Math.floor(Math.random() * length);

console.log(greetings[randomNum]);

````

___

This minimal program will show you how to write JavaScript in a file from the command line, and then execute the code in that file in Node from the command line. 

**Understand**
* Writing a simple JavaScript program in a file
* Running your file in Node
* Node is just JavaScript

**You Need**
* Very basic comfort with using a terminal and simple command line operations
* A command line text editor

___

Open a terminal program and navigate to a folder where you want to save the program you're going to write. For example, I'll put mine on my desktop, so I navigate to ~/Desktop. 

![screenshot of Desktop folder in the terminal](https://github.com/bkager/Node-cookbook/assets/68086185/22b0d6c6-acb6-4165-b483-3c353db71e82)

You're going to create a file and write in it from the command line. For this, you'll need to have a command-line text editor program. If you've worked on the command line much before, you probably already have a favorite. If you haven't, you should have one called nano already on your computer. Type ````nano```` to open an editing window, where you can type anything you like--code, a note to yourself, an entire novel if you want. Try it out, then type CTRL+X to exit nano (and hit N along the way to discard your changes). You should be back at a command prompt so we can create our JavaScript file. 

> Nano uses commands that may not feel intuitive. They're shown at the bottom of the screen and are easy to get used to, but there are many other command line text editors which you may prefer. I like [micro](https://micro-editor.github.io/), which uses the same commands for cut, paste, save, etc. as most modern text editors like Word. Different text editors have their own benefits--I switched to micro because nano doesn't have mouse support in my preferred terminal program, and it was slowly driving me out of my mind. 

To create your program file, 

