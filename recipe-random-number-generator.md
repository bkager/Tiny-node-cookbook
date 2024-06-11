# Random Number Generator

```
const random = (max, howManyNums = 1) => {
  let randomArray = []; 
  while (howManyNums > 0){
    let randomNum = Math.floor(Math.random() * max);
    randomArray.push(randomNum);
    howManyNums -= 1;
  }
  if (randomArray.length > 1) {
  	return randomArray; 
  } else {
  	return randomArray[0];
  }
};

```

___

This recipe doesn't create a full program, just a very simple function to use in trying out the Node shell, aka the Node REPL. REPL stands for "Read-eval-print-loop", and it's a command-line program where you can write JavaScript code and immediately run it. If you have enough practice with JavaScript to be reading this cookbook, you've almost certainly used JavaScript in some sort of REPL before. The Node REPL is a great way to test small things out quickly. 

**Goals for this recipe**
* Try out the Node shell

**You should already understand**
* Very basic command line skills
___

**Getting Started**

Open a terminal program and, at the command prompt, type `node -v`. It should print the version number of Node installed on your system. If you don't get this, go back to the installation instructions and make sure you have Node installed correctly. 

![Screenshot of above instructions carried out](https://github.com/bkager/Node-cookbook/assets/68086185/0f01dfd4-90fd-40e5-949c-ea3dafa5e567)

To open the Node REPL, type `node`.

![Screenshot of instructions carried out. You should get a welcome message, a notice to type ".help" for info, and a prompt.](https://github.com/bkager/Node-cookbook/assets/68086185/2daba6fe-5e56-4ec7-adbb-d42e65849a4b)

**Coding in the REPL**
You now have access to the Node environment. At the prompt, you can write JavaScript code, and it will execute when you press enter. Try it out by assigning a few variables and conducting some simple operations. For example, try typing `const num1 = 10` and enter; then `const num2 = 5` and enter; then `num1 + num2`. It should output 15. This is because the REPL saves your variables in memory for the length of your session. Once you exit the REPL, though, they're removed from memory and you'll start afresh next time. 

![Screenshot of above instructions carried out](https://github.com/bkager/Node-cookbook/assets/68086185/1df77df6-6837-49ec-a252-f27e8f054e77)

If you start entering a multi-line piece of code and press enter at the end of the first line, Node will realize you haven't, for example, closed the brackets on your function and will give you a new line starting with three dots instead of a new prompt. 

![Screenshot illustrating this](https://github.com/bkager/Node-cookbook/assets/68086185/e9ecce5d-b239-496c-9ce0-a455820e65c3)

Once you add the final bracket, it will save your function definition and return to the regular prompt.

![Screenshot illustrating this](https://github.com/bkager/Node-cookbook/assets/68086185/79037c2d-762d-456e-b8da-febe430165d6)

If you're seeing three dots and you didn't mean for that to happen, type `.break` to break out of them. 

You can also enter code by opening the editor by typing `.editor`. This gives you a space to enter multiple lines of code.









### Bonus recipes

* Bonus recipes in bullet points here

### Resources

* The offical Node docs have a good [tutorial on using the REPL](https://nodejs.org/en/learn/command-line/how-to-use-the-nodejs-repl). 
___

### Up Next

Link to next recipe or section
