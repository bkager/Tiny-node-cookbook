## The Node environment vs. the browser enviroment

As we noted in the [introduction](https://github.com/bkager/Node-cookbook/blob/main/introduction.md), JavaScript was originally designed to work inside of web browsers. Node is a newer runtime environment which lets JavaScript work outside of a browser. How does this all work, and how is JavaScript in the browser different from JavaScript in Node?

&nbsp;

## Runtime environments

All programming languages need a runtime environment, the necessary software and hardware that reads and interprets code in a particular language and translates it into binary code that a computer can execute. A JavaScript runtime environment will include things like the JavaScript engine, a section of memory for storing variables, the call stack, the event loop, and so on. (If you're not familiar with these concepts, don't worry about it for right now--the point is just that these are things you need to actually run the code you write.)

Runtime environments also mean that code isn't limited to the basic syntax defined in the programming language itself. Instead, runtime environments provide additional code that extends the capabilities of the programming language. These additional capabilities are built into the software of the runtime environment, which exposes them (makes them available) so code running in the environment can make use of them. 

&nbsp;

## Exploring how a runtime environment extends JavaScript

As an example of this we can look at the JavaScript console, which was probably one of the first things you learned to use in JavaScript. No matter what environment you practiced beginner JavaScript in, you could type something like `console.log(myName)` to print a variable `myName`. However, `console` isn't actually part of the JavaScript language! You can verify this by going to the webpage for [the most recent specification for the language](https://tc39.es/ecma262/) (as of writing, this is ECMA-262). Search for "console" and you won't find it defined anywhere in the official standard for the language. So where is `console.log()` coming from?

The `console.log()` method is provided by the runtime environment. It's an extension to the language, not part of the actual JavaScript language; it's just an incredibly familiar extension that you're probably used to thinking of as a fundamental tool when writing JavaScript code. We can look at how this is works in the browser. Open a web browser and open its tools for inspecting a page. (In Chrome, for instance, right click on the page and click "Inspect", or press Ctrl + Shft + C (Windows) or Cmd + Opt + C (MacOS).) Go to the "Console" tab of the dev tools. Here, you can type JavaScript code and see the output. The familiar `console.log()` method works; try printing anything with it. It works because the browser is providing the function definition for the `console.log()` method and making it available to you. 

Actually, the browser is providing something called `Console`, which you can see documented on MDN [here](https://developer.mozilla.org/en-US/docs/Web/API/console). Take a look at this docs page. Note that it lists Console as a Web API. APIs in general ("application programming interfaces") contain code that applications expose to other developers so that outside code can interact with the application's code. The web APIs listed on MDN are specifically interfaces that browsers provide for JavaScript code running in them to use. They make available features, like the console, that extend the toolkit that JavaScript has available to it in the browser. When you type `let myName = "Bob"` in the browser console window you're writing JavaScript code that depends on the core specifications of the language, and you're relying on the JavaScript engine built into the brower to interpret that code. When you type `console.log(myName)` you're using a feature built into the browser to print your JavaScript variable.

The Console API includes an object called `console`. We could also call this object an "interface"--an interface is just an object containing methods and properties that are being made available to developers.[^1] The console is a "global" object, meaning that any time you're running code in the browser, it's available--you don't have to do anything special to include it in your code. You can just call `console.log()` to invoke the `.log()` method that the `console` object contains. 

The `console` object contains more than just the `.log()` method. Look at its docs page on MDN to see what else is in there. You can even, recursively, log the console object--go to the browser console in the brower dev tools again and type `console.log(console)`. It will print out info about the console object itself, including all the methods you can see on the MDN page you just looked at. 

Lastly, go back to the MDN docs page for the Console API and look towards the bottom for a chart labelled "Browser compatibility". It's there because different web browsers are all separate programs which offer their own features. A Web API provided by Chrome isn't guaranteed to exist in Safari! The extensions that browsers make to JavaScript aren't standardized the way the JavaScript language itself is. The `function` keyword will work the same in any JavaScript runtime, but the `console` may be a bit different from one browser to the next. Notice that even on a much-used feature like the console, there's a bit of variation from one browser to the next in what's supported.

In practice, browsers largely have the same features and agree on how to implement them, enough so that you don't really need to worry about cross-browser differences for the purposes of this cookbook. But it's good to be aware of the issue, and it's a useful reminder here that we're looking at extensions that different runtime environments make to standard JavaScript syntax. 

&nbsp;

## Three buckets of stuff

The point of this digression into browsers is that different runtime environments for JavaScript will provide different extensions to the language. The core JavaScript language is the same whether you're writing it to work in a browser or in Node, but browsers will give you different interfaces to take advantage of than Node will. Browsers mostly add functionality related to viewing and manipulating html documents and doing other web-related tasks in a graphical interface; this makes sense, since the whole purpose of a browser is to interact with the web. Node, on the other hand, is is designed to run JavaScript code that does things the browser doesn't, so it provides interfaces for tasks like creating the backends (non-visible parts) of websites and interacting with the computer that the program is running on via filesystem operations and so on. 

Right now, you can think of JavaScript in terms of three buckets of stuff: the core JavaScript language, JavaScript interfaces that extend what you have available in the browser, and JavaScript interfaces that extend what you have available in Node. 

This is worth emphasizing because, if you've learned beginner JavaScript to the point that you're reading this book, you may have some JavaScript skills that you don't realize are browser-only. If you try to use these things in Node, they won't work. For example, you might know the `alert()` or `prompt()` methods. These are part of the browser, not the JavaScript language--they exist to give users popups in the graphical environment of a browser. (They're more properly called `window.prompt()` and `window.alert()`, and are methods belonging to the [Window Web API](https://developer.mozilla.org/en-US/docs/Web/API/Window) of the browser.) Node doesn't have a graphical interface in the same way, so the Window API and these methods aren't implemented in it.

Sometimes browsers and Node provide parallel functionality. Both have a `console` object with a `console.log()` method, for instance, because a console is handy in both runtime environments. But there are more things that aren't duplicated across runtime environments than things that are. Node is intended to complement browser runtime environments and to do things they can't, not to replace them.

Because different things exist in Node than in the browser, you need to look at different documentation for each runtime environment. For example, go to MDN's [JavaScript docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) and search for `http.createServer()`, a method you'll use a lot in Node. You won't find it documented there, because MDN documents specifically browser-based JavaScript. Instead, you have to go to [this page](https://nodejs.org/docs/latest/api/http.html) in the Node docs to see information about it. (And the flip side: you can see the `document.getElementById()` method [here](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById), but nowhere in the Node docs, because the Document interface exists in the browser but not in Node.) 

Another way to think about the division of functionality between the browser and Node is to remember that, wherever your code runs, the appropriate runtime environment has to be available. If you build a website in JavaScript, any users who visit it online need to have a runtime environment for your JavaScript code. That's not a problem, because all modern browsers are JavaScript runtime environments--a user looking at your site in Chrome or Safari is automatically loading your code in a JavaScript runtime environment. You can write JavaScript and know that your users have methods like `alert()` and `document.getElementById()` in the browser on their own machine, so when they go to your website, the JavaScript code embedded in it can run correctly. However, most users who aren't developers won't have Node installed, so users generally can't run code with Node-only functionality. You could say that browser JavaScript is end-user focused, while Node JavaScript is developer-focused. 

&nbsp;

## The browser runtime environment

The best documentation for JavaScript is Mozilla's, at [MDN](https://developer.mozilla.org/en-US/). MDN includes guides, tutorials, and comprehensive documentation for a variety of web technologies, including JavaScript, browser-specific Web APIs for JavaScript, HTML, CSS, HTTP and more. Because it documents both fundamental JavaScript syntax and Web APIs that only work in the browser, I found MDN somewhat confusing before I understood the difference between the two. Just keep an eye on which section of the site you're in: if you're looking at the [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript) reference you're looking at documentation of standard JavaScript features, and if you're looking at the [Web API](https://developer.mozilla.org/en-US/docs/Web/API) reference, you're looking at browser-only features that aren't relevant to Node. 

A few Web APIs that you might or might not have encountered include: 

* The DOM (Document Object Model) and the Document interface, used to represent and manipulate elements of HTML pages
* The Fetch API, used in making HTTP requests
* The XMLHttpRequest API, an older API for HTTP requests
* The Window interface
* The Console API

&nbsp;

## The Node runtime environment

Documentation of Node-specific features can be found [here](https://nodejs.org/docs/latest/api/). The interfaces provided by Node are called the core Node modules, and they're the main topic of this book.

&nbsp;

## Summary 
* Web browsers and Node are runtime environments for JavaScript. Runtime environments are the software and hardware that you need to make code actually work.
* Runtime environments can provide interfaces which extend the capabilities of code that runs inside of them.
* Browsers and Node both provide JavaScript interfaces, but different ones. Some interfaces are browser-only, some are Node-only, and some exist in both environments.
* The actual JavaScript language is the same no matter where you use it.
* Concepts you should understand include:
  * Runtime environments
  * APIs/interfaces
  * JavaScript engines

    
&nbsp;

___

## Resources

### Up Next

Link to next recipe or section

______
[^1]: Interfaces and APIs are not exactly the same thing. In this case, the big-C Console API and the small-c console object/interface are effectively identical, but an API will often have more than one interface in it. More on the topic in this section **XXX ADD LINK XXX**.
