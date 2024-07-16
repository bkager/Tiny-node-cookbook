# The Node environment vs. the browser enviroment

As we noted in the [introduction](https://github.com/bkager/Node-cookbook/blob/main/introduction.md), JavaScript was originally designed to work inside of web browsers. Node is a newer program which lets JavaScript work outside of a browser. How does this all work, and how is JavaScript in the browser different from JavaScript in Node?


has multiple software environments in which it can run. Web browsers are the original runtime environment of JavaScript code, while Node is a newer JavaScript runtime environment which lets JavaScript code work outside of browsers. 


-All code needs a runtime environment
 -Translates it into machine code, etc. 
-The runtime environment provides the JS engine
 -The code for the language itself
- The runtime env. provides other infrastructure
 - Event loop, bindings, etc. 
-The runtime environment also provides extra stuff 
 -Example of something not in the JS core lang but in Node or browser
 -Extends the abilities of the language

-Stuff browsers and Node both provide
-Stuff only in the browser
-Stuff only in Node



# Runtime environments

All programming languages need a runtime environment. The runtime environment is the collection of software and hardware that reads and interprets code in a particular language and translates it into binary code that a computer can actually execute. A JavaScript runtime environment will include things like the JavaScript engine, a section of memory for storing variables, the call stack, the event loop, and so on. (If you're not familiar with these concepts, don't worry about it for right now--the point is just that these are things you need to actually run the code you write.)

Runtime environments also mean that code isn't limited to the basic syntax defined in the programming language itself. Instead, runtime environments provide additional code that extends the capabilities of the programming language. These additional capabilities are built into the software of the runtime environment, which exposes it (makes it available) to code running in the environment to use. 

# Exploring the browser runtime environment and what it adds to JavaScript

As an example of this we can look at the JavaScript console, which was probably one of the first things you learned to use in JavaScript. No matter what environment you practiced beginner JavaScript in, you could type something like `console.log(myName)` to print a variable `myName`. However, `console` isn't actually part of the JavaScript language! You can verify this by going to the webpage for [the most recent offical specification for the language](https://tc39.es/ecma262/) (as of writing, this is ECMA-262). Search for "console" and you won't find it. So where is `console.log()` coming from?

The `console.log()` method is provided by the runtime environment. It's an extension to the language, not part of the actual JavaScript language; it's just an incredibly familiar extension that you're probably used to thinking of as a fundamental tool when writing JavaScript code. We can look at how this is works in the browser. Open a web browser and open its tools for inspecting a page. (In Chrome, for instance, right click on the page and click "Inspect", or press Ctrl + Shft + C (Windows) or Cmd + Opt + C (MacOS).) Go to the "Console" tab of the dev tools. Here, you can type JavaScript code and see the output. The familiar `console.log()` method works; try printing anything with it. It works because the browser is providing the code for the `console.log()` method and making it available to you. 

Actually, the browser is providing a whole object called `console`, which you can see documented on MDN [here](https://developer.mozilla.org/en-US/docs/Web/API/console). Take a look at this docs page. Note that it lists the console as a Web API. APIs in general ("application programming interfaces") are code that applications expose to other developers as an interface where outside code can interact with the application's code. The web APIs listed on MDN are specifically interfaces that browsers provide for JavaScript code running in them to use. They make available features, like the console, that extend the toolkit that JavaScript in the browser can use. When you type `let myName = "Bob"` in the browser console window you're writing JavaScript code that depends on the core specifications of the language, and you're relying on the JavaScript engine built into the brower to interpret that code. When you type `console.log(myName)` you're using a feature built into the browser to print your JavaScript variable.

The Console API includes an object called `console`. We could also call this object an "interface"--an interface is just an object containing methods and properties that are being made available for developers to use. The console is a "global" object, meaning that any time you're running code in the browser, it's available--you don't have to do anything special to make it available to you. You can just call `console.log()` to invoke the `.log()` method that the `console` object contains. 

The `console` object contains more than just the `.log()` method. Look at its docs page on MDN to see what else is in there. You can even, recursively, log the console object--go to the browser console in the brower dev tools again and type `console.log(console)`. It will print out info about the console object itself, including all the methods you can see on the MDN page you just looked at. 

Lastly, go back to the MDN docs page for the Console API and look towards the bottom for a chart labelled "Browser compatibility". It's there because different web browsers--Chrome, Safari, Firefox, and so on--are all separate programs which offer their own features. A Web API provided by Chrome isn't guaranteed to exist in Safari! The extensions that browsers make to JavaScript aren't standardized the way the basic JavaScript language itself is. The `function` keyword will work the same in any JavaScript runtime, but the `console` may be a bit different from one browser to the next. Notice that even on a very well-supported and common feature like the console, there's a bit of variation from one browser to the next in what's supported.

In practice, browsers largely have the same features and agree on how to implement them, enough so that you don't really need to worry about cross-browser differences for the purposes of this cookbook. But it's good to be aware of the issue, and it's a useful reminder here that we're looking at things that different runtime environments add their own extensions to basic JavaScript syntax. 

## The Node runtime environment





***


-any code needs a runtime environment
-There's the core programming language
-There's stuff the runtime environment provides. These are _program features_, not part of the core language
-Stuff that is part of the JS language
-Stuff browsers and Node both provide
 -JS engine
 - event loop
-Stuff only browsers provide (briefly)
 - Web APIs
-Stuff only Node provides
 - Core Node modules
 -  





Because of this, you also need to look at different documentation for Node than for browser JavaScript, because a lot of what you'll use in Node simply doesn't exist in the browser. For example, go to MDN's [JavaScript docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) and search for `http.createServer()`, a method you'll use a lot in Node. You won't find it documented there. Instead, you have to go to [this page](https://nodejs.org/docs/latest/api/http.html) in the Node docs to see information about it. (And the flip side: you can see the `document.getElementById()` method [here](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById), but nowhere in the Node docs, because the Document interface is something the browser provides for working with web pages--it doesn't exist in Node.)


























































## Use H2 for subheadings


&nbsp;

## Summary 
* Concepts you should understand include:
  * Runtime environments
  * APIs/interfaces
  *  

* Bonus concepts
  * Garbage collection  
&nbsp;

___

## Bonus recipes

* Bonus recipes in bullet points here

 &nbsp;

## Resources

### Up Next

Link to next recipe or section
