---
title: Introduction to Node.js
layout: learn
authors: flaviocopes, potch, MylesBorins, RomainLanz, virkt25, Trott, onel0p3z, ollelauribostrom, MarkPieszak, fhemberger, LaRuaNa, FrozenPandaz, mcollina, amiller-gh, ahmadawais, saqibameen, dangen-effy, aymen94, benhalverson
---

# Introduction to Node.js

Node.js is a free and cross-platform tool that allows you to run JavaScript code outside the browser. It’s used in many types of projects.

Node.js runs Google Chrome’s V8 JavaScript engine outside the browser, which makes it very fast.

A Node.js app runs in a single process and doesn’t create a new thread for every request. Instead, it uses asynchronous input/output features to avoid blocking code.

When Node.js performs an operation like reading from a file or database, it doesn’t stop everything. It continues running and finishes the task once the result is ready.

This means Node.js can handle thousands of users at once without slowing down or needing complex thread management.

This makes it easier for frontend developers (who already use JavaScript) to write backend code too, without learning a new programming language.

With Node.js, you can use the latest JavaScript features because it doesn’t depend on the user's browser. You control which version to use by choosing the Node.js version.

## An Example Node.js Application

The most common example Hello World of Node.js is a web server:

```cjs
const { createServer } = require('node:http');

const hostname = '127.0.0.1';
const port = 3000;

const server = createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});

```mjs
import { createServer } from 'node:http';

const hostname = '127.0.0.1';
const port = 3000;

const server = createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});

To run this code, save it as a file named server.js and run it using the command node server.js in your terminal.
If you use the ES module version, save it as server.mjs and run it with node server.mjs.

This example uses the built-in http module in Node.js.

Node.js has a powerful standard library, including support for network and server functions.

The createServer() function makes a new web server.

The server listens on the given host and port. When it starts, it runs a function to show that the server is working.

Every time the server gets a request, it triggers the request event. This gives you two objects: req (request) and res (response).

The request object contains details like headers and data. We’re not using it in this simple example.

The response object is used to send a reply back.

In this example:

res.statusCode = 200;
// We’re setting the HTTP status code to 200, which means success.

res.setHeader('Content-Type', 'text/plain');
// We set the content type to plain text.

res.end('Hello World\n');
// We send the text “Hello World” and end the response.

If you haven’t already installed Node.js, you can download it from https://nodejs.org/en/download.

