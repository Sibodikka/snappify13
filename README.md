# snappify13

Snappify13
A simple web framework that is simple and aims to be fast

Supports async/await and ES6 features

Goals
Stay updated with latest JS features
Always improving performance
Add useful features that aren't expensive
Routing explanation
Snappi has a very simple routing pipe just like popular frameworks, ie: express

use -> route handlers

Example
const Snappi = require("Snappi");

const server = new Snappi();

server.use(async (req, res) => {
  req.test = "hello";
});

server.use((req, res, next) => {
  console.log("yay :^)");
});

server.use((req, res) => {
  console.log(req.test); //would return "hello"
});

server.route("GET", "/", (req, res) => {
  res.end("Hello");
});

server.listen(80);
Both async and regular functions work, so do (req, res, next) for some express plugin/middleware support

Additional features
Visit /tests/ to see additional tests

You're able to chain functions or pass objects to a route

server.route(
  "GET",
  "/",
  { test: "hello" },
  (req, res) => {
    console.log(req.test); //would return hello
  },
  (req, res) => {
    res.end("hey");
    //chaining works as such
  }
);
  path = path.split('/')
  return path
}

module.exports = Snappi
