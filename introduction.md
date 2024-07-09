
## Welcome to Node!

If you're reading this, you're presumably interested in working with JavaScript in some capacity. Maybe you've already started learning Node, or maybe this is your first encounter with it. What the heck is Node, and why do you need to know it to write modern JavaScript?

## What Node is and does

Originally, JavaScript only worked inside web browsers and was used primarily for programming the frontends of websites (the parts visitors could see and interact with). Browsers provided JavaScript's first runtime environment, meaning the software infrastructure that allowed JavaScript code to be executed. The browser contained the core JavaScript engine and ways to interact with web documents, make http requests to other machines, and other functionality. If you've used MDN's comprehensive [JavaScript documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference), what it covers is specifically this browser-based JavaScript. JavaScript in the browser has access to tons of browser-related functionality, but runs in a sandbox that limits it from doing many other things, like freely interacting with your computer's filesystem or replying to http requests from other computers (which means you can't create a web server with it). You used to be able to create a website's frontend in JavaScript, but to create the backend--servers, database connections, etc.--you had to use a different programming language. 

Node, released in 2009, is an alternative runtime environment that lets JavaScript run somewhere other than the browser. Like browsers, Node provides a JavaScript engine and the rest of the software environment needed to execute JavaScript code. The JavaScript language you use in Node is the same as the JavaScript you use in the browser. However, Node provides access to very different things than browsers do. Node lets your JavaScript code work with files on your computer and the operating system, reply to http requests, connect to databases, and conduct other useful operations. However, it doesn't have access to things like the browser's DOM, because it's running in a completely different program than the browser. The Web APIs listed [here](https://developer.mozilla.org/en-US/docs/Web/API), for example, are features of the browser software that aren't available in Node. (A few, like the Fetch API, have equivalents recreated in Node.)  

That last point is worth reiterating a bit because it's so fundamental that a lot of tutorials just forget to explain it, and I've seen people learning Node, including myself, confused by it for way longer than they needed to be. Node and a web browser are two completely different programs. They both run JavaScript, but they provide very different features and you use them to do different things with the language. You'll often use browser JavaScript and Node JavaScript together to write different parts of a project, and you will store them side by side in a project's files, but you could compare this to putting a photo, a music file, and a text document in the same folder on your computer desktop--these things can be stored together, but they need to run in different programs, and you'll have problems if you try to open a music track in a text editor. 

Because of this, you also need to look at different documentation for Node than for browser JavaScript, because a lot of what you'll use in Node simply doesn't exist in the browser. For example, go to MDN's [JavaScript docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) and search for `http.createServer()`, a method you'll use a lot in Node. You won't find it documented there. Instead, you have to go to [this page](https://nodejs.org/docs/latest/api/http.html) in the Node docs to see information about it.

You can think of three buckets of JavaScript stuff that you want to be able to distinguish right now: the core JavaScript language that is the same whether you're using it in the browser or in Node, the browser-related APIs that web browsers provide to extend JavaScript's capabilities in the browser, and the non-browser APIs that Node provides to extend what JavaScript can do outside of the browser. 

You'll run Node JavaScript primarily from the command line, and browser JavaScript from inside a browser. Browser JavaScript can communicate with Node JavaScript through HTTP requests, which means you can create the frontend of a website in browser JavaScript and the backend server in Node JavaScript and have the two sides talk to each other with http to create a cohesive user experience. Node and browsers aren't an either/or; they're complementary environments, and you need to use both to get the most out of JavaScript. 

Node is extremely popular and there are many, many extensions, libraries, frameworks, etc. which people have created to extend Node's capabilities and make working with it easier. For example, Express is a wildly popular framework which makes writing servers in Node less fussy. This cookbook, at least for the moment, deals only with basic ("vanilla") Node. It's good to know the fundamentals, and also I feel that vanilla Node tends to be badly explained while other systems like Express often have much better tutorials available.  

Lastly, Node was the first way to run JavaScript outside the browser, but there are now other non-browser JavaScript runtimes as well. [Deno](https://deno.com/) and [Bun](https://bun.sh/docs/runtime/jsx) are two Node alternatives. Different backend runtimes come with different advantages and philosophies. Deno, for instance, is more security-focused than Node. 

## How this cookbook is organized

This book has two main sections: 
1) Node Basics: A Minimal Introduction to Some Important Bits
2) Beyond the Basics

The first section, Node Basics, introduces some fundamental Node concepts and the Node docs, and then covers a number of the topics you're most likely to need to know at a level of detail that will get you started. This includes using the Node REPL, writing and publishing simple scripts, simple filesystem operations, and creating a server in vanilla Node. Think of this section as a quick start guide to Node. It's going to work best if you go through it in order, since the recipes build on each other. 

The second section, Beyond the Basics, returns to many of these topics in more detail. It's easier to skip around in this section without missing essentials. 

## Keeping your own cookbook / notes

It's a good idea to start your own collection of useful code examples as you go. If you save templates for how to write a server, how to access a file, etc. you'll come back to them over and over. 

## Installing Node

As with many things Node, I find the offical instructions for installing it assume more knowledge than you might have right now. If you want very clear, step-by-step directions, Digital Ocean has a nice set of Node tutorials that starts with installation [here](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-and-create-a-local-development-environment-on-macos). Note that you can switch between instructions for different operating systems.

Node's own instructions are [here](https://nodejs.org/en/learn/getting-started/how-to-install-nodejs) and may be fine if you're more experienced. 
