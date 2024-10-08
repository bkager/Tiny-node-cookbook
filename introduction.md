
## Welcome to Node!

If you're reading this, you're presumably interested in working with JavaScript in some capacity. Maybe you've already started learning Node, or maybe this is your first encounter with it. What _is_ Node, and why do you need to know it to write modern JavaScript?

## What Node is and does

Originally, JavaScript only worked inside web browsers and was used primarily for programming the frontends of websites (the parts of a website that visitors can see and interact with). Browsers were JavaScript's first runtime environment, meaning the software infrastructure that supported JavaScript code and translated what developers wrote into instructions the computer could understand. The browser provided the JavaScript engine and gave websites written in JavaScript ways to interact with web documents, make http requests to other machines, and other functionality. JavaScript in the browser has access to tons of browser-related functionality, but runs in a sandbox that limits it from doing many other things, like freely interacting with your computer's filesystem or replying to http requests from other computers (which means you can't create a web server with it). Originally, you could create a website's frontend in JavaScript, but to create the backend—servers, database connections, etc.—you had to switch to a different programming language. 

Node, released in 2009, is an alternative runtime environment that lets JavaScript run somewhere other than a browser. Like browsers, Node provides a JavaScript engine and the rest of the software environment needed to execute JavaScript code. The JavaScript language you use in Node is the same as the JavaScript you use in the browser. However, Node provides access to very different things than browsers do. Node lets your JavaScript code work with files on your computer and the operating system, reply to http requests, connect to databases, and conduct other useful operations. However, it doesn't have access to things like the browser's DOM, because it's running in a completely different program than the browser.

That last point is worth reiterating because it's so fundamental that many tutorials just forget to explain it. Node and a web browser are two completely different programs. They both run JavaScript code, but they provide very different features and you use them to do different things with the language. The brower provides webpage-related functionality, while Node mostly provides functionality related to the computer it's running on. You'll often use browser JavaScript and Node JavaScript together to write different parts of a project, and you will store them side by side in a project's files, but you could compare this to putting a photo, a music file, and a text document in the same folder on your computer desktop—these things can be stored together and they might all relate to the same project, but they need to run in different programs, and you'll have problems if you try to open a music track in a text editor. 

<img width="690" alt="Visualization of Node functions vs browser functions as described above" src="https://github.com/user-attachments/assets/58a78444-df26-4178-8a6c-49762bdee620">

You'll run Node-based JavaScript primarily from the command line, and browser-based JavaScript from inside a browser. Browser JavaScript can communicate with Node JavaScript through HTTP requests, which means you can create the frontend of a website in browser JavaScript and the backend server in Node JavaScript and have the two sides talk to each other with http to create a cohesive user experience. Node and browsers aren't an either/or; they're complementary environments, and you need to use both to get the most out of JavaScript. 

![Visualization of a Node server communicating with a website created in browser JavaScript via http requests and responses. The code for both the webpage and server live on your filesystem as part of the same project.](https://github.com/user-attachments/assets/001bda84-fe5c-479e-b87a-129452c9fc8d)

Node is extremely popular and there are many, many extensions, libraries, frameworks, etc. which people have created to extend Node's capabilities and make working with it easier. For example, Express is a popular framework which makes writing servers in Node less fussy. This cookbook, at least for the moment, deals only with basic ("vanilla") Node. It's good to know the fundamentals, and also I feel that vanilla Node tends to be badly explained while extensions like Express often have much better tutorials available.  

Lastly, Node was the first way to run JavaScript outside the browser, but there are now other non-browser JavaScript runtimes as well. [Deno](https://deno.com/) and [Bun](https://bun.sh/docs/runtime/jsx) are two Node alternatives. Different backend runtimes come with different advantages and philosophies. Deno, for instance, is more security-focused than Node. 

## How this cookbook is organized

This book has two main sections: 
1) Node Basics: A Minimal Introduction to Some Important Bits
2) Beyond the Basics

The first section, Node Basics, introduces some fundamental Node concepts and the Node docs, and then covers a number of the topics you're most likely to need to know at a level of detail that will get you started. This includes using the Node REPL, writing and publishing simple scripts, simple filesystem operations, and creating a server in vanilla Node. Think of this section as a quick start guide to Node. It's going to work best if you go through it in order, since the recipes build on each other. 

The second section, Beyond the Basics, returns to many of these topics in more detail. It's easier to skip around in this section without missing essentials. 

## Keeping your own cookbook / notes

It's a good idea to start your own collection of useful code examples as you go. If you save templates for how to write a server, how to access a file, etc. you'll come back to them over and over. Personally, I keep an extensive notebook in Notion, including my notes on coding topics and languages, templates and examples of code, a personal wiki of coding concepts, notes on projects, and so on. I also tend to rebuild my own documentation for a language as I learn it. Often the best way to learn a topic is to have to explain it. More on this when we look at [reading the Node docs](https://github.com/bkager/Node-cookbook/blob/main/informational-reading-the-Node-docs.md) and [creating your own](https://github.com/bkager/Node-cookbook/blob/main/informational-creating-your-own-docs.md). 

## Installing Node

As with many things Node, I find the offical instructions for installing it assume more knowledge than you might have right now. If you want very clear, step-by-step directions, Digital Ocean has a nice set of Node tutorials that starts with installation [here](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-and-create-a-local-development-environment-on-macos). Note that you can switch between instructions for different operating systems.

Node's own instructions are [here](https://nodejs.org/en/learn/getting-started/how-to-install-nodejs) and may be fine if you're more experienced. 

___

## Resources

* This section will regularly have links to further resources on the topic, and there's a collected [bibliography](https://github.com/bkager/Tiny-node-cookbook/blob/main/resources.md) at the end of the book. 

### Up Next

Link to next recipe or section
