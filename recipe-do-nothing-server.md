
# Do-Nothing Server

```
const http = require("http");

const server = http.createServer();

server.listen(3000, () => console.log("Server is listening on port 3000. It doesn't do anything, though!"));

```

___

This recipe shows you how to create an absolutely minimal server in vanilla Node. 

**Goals for This Recipe**
* Set up the basis for a server in vanilla Node
* Use the http module of Node

___

A server is a program that waits for requests to arrive at a specific port on a computer, and then does something in response. **(XXX EXPLAIN PORTS)**. You write a bit of code that creates a server, and then you tell it to listen to a particular port. If a request arrives to that port, the operating system knows that the server is interested and passes the request to it.

In this recipe you're going to set up a server and tell it to listen to a port, but that's it--your server is not going to do much other than exist. You'll add code for the server to actually respond to requests in future recipes. 

**Setup**

Create a file called `server.js`. 

To create a server, you're going to be using methods from the Node `http` module. This is a core Node module, but not a global one, so you have to import it. Do that at the top of the file with `const http = require("http")`. 

The `http` module contains various methods, properties, and classes for dealing with http requests as both a client and as a server. For now, you need two methods, one to create your server and one to tell it to listen on a port. 

**Creating the Server**

A Node server is an object--it's an instance of the Server interface, which is part of the http module. The top level of the http module also contains a method, `http.createServer()`. Look over the documentation for the [http module](https://nodejs.org/docs/latest/api/http.html). You can find the documentation for the Server interface in the list of the module's contents at Class: http.Server. Then scroll to the botton of the list, under the documentation for the interfaces, to see the properties and methods that exist at the top level of `http`.

The `http.createServer` method is listed as `http.createServer([options][, requestListener])`, showing that it can take two arguments, both of them optional. You're not going to include any arguments for the moment. 

In your `server.js` file, under the module import, type `const server = http.createServer()`. This creates a server and saves it to the variable `server` for later use. 

```
const http = require("http");

const server = http.createServer();

```
Since your server is an instance of Server, glance over the documentation for the Server interface. Servers are event emitters, and there's a list of the types of events they can emit. There's also a number of methods and properties you can call on your server object. 

**Setting the Server to Listen**

The only server method you need right now is `server.listen()`, which tells your server instance to start listening for incoming requests on a port. Add the line `server.listen()` to your file. Note that `server` here means your specific server instance, the one you created and saved to the `server` variable.

```
const http = require("http");

const server = http.createServer();

server.listen();
```
You now have a server object which will start listening when you run the `server.js` file.

The `http.server.listen()` method accepts arguments. The Node docs do not actually tell you this. Instead, you have to go look at the docs for the `net.server.listen()` method, which you'll note is ~~at the bottom of a locked file cabinet in a disused lavatory with a sign on the door reading 'Beware the Leopard'~~ in the docs for an entirely different module. I'm sure this made sense to someone, somewhere, at some point. 

You're going to pass your `server.listen()` method two arguments. The first is the number of the port you want it to listen on. Modify the last line of your file: 
```
const http = require("http");

const server = http.createServer();

server.listen(3000);
```
When you run the file, you'll now have a server listening on port 3000. 

`server.listen()` can also accept a second argument, a callback function which runs when the server starts listening. Usually people use this to console.log a message that the server is running, because it's nice to get some confirmation that it's working. Add a callback like this: 
```
const http = require("http");

const server = http.createServer();

server.listen(3000, () => console.log("Server is listening on port 3000. It doesn't do anything, though!"));
```
When you run server.js, your code will create a server, set it to listen on port 3000, and output a message telling you it's listening.

To see this, on the command line, navigate to the folder holding your `server.js` file and type `node server.js` to run it. You should see your confirmation message as output!

To stop your server, press `ctrl + C`.

### Bonus recipes

**Another Way to Check That Your Server Is Listening**

You can get confirmation that your server is working in another way, too. Open a new tab in a web browser and type `http://localhost:3000/` in the address bar. Your browser (acting as a client) opens a connection to port 3000 on your machine. The server notices this and sends back a confirmation that it's listening. This is entirely separate from the confirmation message you've coded it to output when it starts listening; the browser and the server are just waving at each other to confirm they can establish a connection. Only then does your browser send an actual http request. (In this case, it's just asking the server to send it whatever default webpage, etc. the server delivers if you go to that address, just the way your browser expects to be sent the main page of wikipedia if you go to the address https://www.wikipedia.org/.)

Because the browser knows that the server is listening and they have a connection, it will wait for the server to send back a response. However, you haven't given your server any way to respond to the browser yet. You'll see the browser sadly loading and loading and loading before finally timing out. It can see that the lights are on, but no one is coming to the door. 

For comparison, go to `http://localhost:3001/`, a port you *don't* have a server listening on. You'll see the browser give up immediately and tell you it can't connect, since there wasn't a server there at all to get its hopes up.

___

### Up Next

Link to next recipe or section
