# The Node environment vs. the browser enviroment

As we noted in the [introduction](https://github.com/bkager/Node-cookbook/blob/main/introduction.md), JavaScript has multiple software environments in which it can run. Web browsers are the original runtime environment of JavaScript code, and provide web-related functionality. Node is another JavaScript runtime environment which lets JavaScript code work outside of browsers. 


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

All programming languages need a runtime environment. The runtime environment is the collection of software and hardware that reads and interprets code in a particular language and translates it into binary code that a computer can actually execute. A JavaScript runtime environment will include things like the JavaScript engine, a section of memory for storing variables, the call stack, the event loop, and so on. (If you're not familiar with these concepts, don't worry about it for right now--the point is just that these are things you need to actually run the code you write.)

Runtime environments can do more than just execute code written in the basic syntax of the programming language. They can also provide code that extends the






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
* Bullet points

&nbsp;

___

## Bonus recipes

* Bonus recipes in bullet points here

 &nbsp;

## Resources

### Up Next

Link to next recipe or section
