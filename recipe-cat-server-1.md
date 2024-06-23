# Cat Server 1

```
const http = require("http");

const server = http.createServer((req, res) => {
  console.log("req.headers: ", req.headers);
  console.log("req.method: ", req.method);
  console.log("req.url: ", req.url);
});

server.listen(3000, () => console.log("Server is listening on port 3000. Meow!"));

```

## Goals

This recipe gives your basic server the ability to do something with an incoming request. 

* Add a basic request handler to a server
* Inspect an incoming http request
* Understand the IncomingRequest class

 &nbsp;
 
# Introduction

In the last recipe, you created a server and set it to listen on a port. If you did the bonus recipe, you also saw that your browser could try to open a webpage at that port, and was very confused that the server didn't do anything. In this recipe, we're going to give the server the ability to look at an incoming http request and do something with it, although it still won't respond to the browser. 

 &nbsp;
 
## Set Up A Server

Create a file called cat-server.js. In it, save the following code: 

```
const http = require("http");

const server = http.createServer();

server.listen(3000, () => console.log("Server is listening on port 3000. Meow!"));
```

This is the same thing you did in the last recipe--create a server and set it to listen for http requests, but not give it a way to respond to them. 

On the command line, type `node cat-server.js` to start your server and see it output its confirmation message. Meow! 

Type ctrl+C to stop your server.

&nbsp;

## The Request Handler

When you set up your first server, we noted that the `http.createServer()` method can take two optional arguments. One of these arguments is a callback function called the request handler. The request handler is where you put the code for what the server should actually do when an http request arrives.

This basic pattern looks like: 
```
const http = require("http");

const server = http.createServer((reqest, response) => {
  //Respond to requests in here
});

server.listen(3000, () => console.log("Server is listening on port 3000. Meow!"));
```
The request handler `(request, response) => {}` has two parameters, `request` and `response`, which are usually abbreviated to `req` and `res`. There are two important points here: 
   1) The request handler is called automatically whenever an http request arrives.
   2) The http request object and an http response object are automatically passed to the request handler.

Then an http request arrives at the server, Node reformats it into a JavaScript object that we can work with. Node then passes this object to your request handler as its first argument. Again, you don't have to do anything to make this happen other than add `req` or `request` or some other name as a parameter--the request handler is a build-in feature of Node, and Node knows to pass it the request object as the first argument without being asked. You can name it whatever you like, but `req` is conventional.
 
 &nbsp;
 
## Logging the Request Object

The request object contains a huge amount of data. To see what this looks like, modify cat-server.js so that when a request comes in, the server logs the request object as output. Also, go ahead and shorten the parameters 'request' and 'response' to 'req' and 'res' if you like. 
      
```
const http = require("http");

const server = http.createServer((req, res) => {
  console.log(req);
});

server.listen(3000, () => console.log("Server is listening on port 3000. Meow!"));
```

Run your server code from the command line (`node cat-server.js`). You'll see your 'Server is listening' message again. Everything so far has happened in the Node runtime environment that you're accessing from the command line.

Now, open a browser and go to `http://localhost:3000/`. Your browser is acting as a client and trying to connect to your server. Just by trying to connect, it has sent your server an http request. No joy, browser! The server still can't send a response back. However, back on the command line, your server program shows that it has received the browser's request by logging the request object to the command line. 

> Side note: If you've played around in the browser dev tools before, you may be wondering why the console.log statement prints to the command line instead of to the console in the browser, where you've probably seen output before. The answer is that the Node runtime environment, which is where cat-server.js is running, sends output to the command line, and JavaScript code that's running in the browser runtime environment prints console.log statements to the browser console. The browser console doesn't currently have access to anything that's going on in the Node runtime, because the server hasn't sent anything from Node back to the browser yet. In the next recipe we'll change this.

 &nbsp;
 
## Examining the Request Object

Ok, so let's look at the request object that your server logged. That's a lot of data. Fortunately, you can ignore 99% of what's in it. Do scroll through it and see where you can spot familiar things, though. 

The request object is an instance of the IncomingMesagge class, which is part of the `http` module. Instances of IncomingMessage are event emitters and have properties, methods, and events that make it easier to work with requests. Take a look at the docs. The three properties that we care about right now are `message.headers`, `message.method`, and `message.url`. As we saw with servers, `message` here means any instance of the IncomingMessage class. People usually name their IncomingMessage instances `req` when they name them in the parameters of the request handler, so if you follow that convention you'll access these properties in your code by typing `req.headers`, `req.method`, and `req.url`, and that's usually what you'll see in code examples. 

All of these properties help to get us access to useful information from the request object. `message.method` returns the http verb used for the request (GET, POST, etc.). `message.url` returns the path the request was sent to. `message.headers` returns the headers of request object, but formatted into a more user-friendly object than way they appear on the request object itself. 

Update your code so that when your server receives a request, it logs the headers, method, and url. You'll eventually want these three pieces of information when you give your server a way to send back a response. Here you're just seeing how to access them. 

```
const http = require("http");

const server = http.createServer((req, res) => {
  console.log("req.headers: " + req.headers);
});

server.listen(3000, () => console.log("Server is listening on port 3000. Meow!"));
```

&nbsp;

## Summary

* The `http.createServer()` method can (and usually will) receive a callback called the request handler as an argument.
* The request handler has two parameters, usually called req and res.
* When a request reaches the server, Node formats the http request as an instance of the IncomingMessage class of the http module.
* Node then automatically passes this request object to the request handler as its first argument. You can access it inside the request handler as `req`, or whatever you named the first parameter.
* The request object, as an instance of IncomingMessage, has useful methods and properties on it for handling requests.
* Three methods to know for now are `message.headers`, `message.method`, and `message.url`, which you'll usually call on your `req` object as `req.headers`, `req.method`, and `req.url`.

  &nbsp;

___


## Bonus recipes

* Look through the http module docs and see what else belongs to the http.IncomingMessage class.  
* I mentioned that `message.headers` returns a version of the http request headers that has been formatted to be more user-friendly. Add some code to your server to log `message.rawHeaders` if you want to see what the headers look like before this reformatting. 


 &nbsp;

## Up Next

Link to next recipe or section
