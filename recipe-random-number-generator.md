# Random Number

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

This recipe doesn't create a full program, just a very simple function to use in trying out the Node shell, aka the Node REPL. REPL stands for "Read-eval-print-loop", and it's a program where you can write JavaScript code and immediately run it in a terminal. If you have enough practice with JavaScript to be reading this cookbook, you've almost certainly used JavaScript in some sort of REPL before. The Node REPL is a great way to test small things out quickly. 

**Goals for this recipe**
* Try out the Node shell

**You should already understand**
* Very basic command line skills
___

Open a terminal program and, at the command prompt, type `node -v`. It should print the version number of Node installed on your system. If you don't get this, go back to the installation instructions and make sure you have Node installed correctly. 



**Use bold for subheadings**

### Bonus recipes

* Bonus recipes in bullet points here

___

### Up Next

Link to next recipe or section
