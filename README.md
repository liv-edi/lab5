## Lab 5

In this lab we downloaded and installed Postmen, created a CIT281 collection of folders, creasted a Node.js and Fastify server application using GET that responded with JSON, created an array of students, used portman to test GET routes, added POST handling server apllication and respond with JSON, and used postman and POST request.

Technologies used in this lab:
- VSCode
- Node.js
- Fastify
- Postman

The purpose of this lab was to teach us more efficent way to test routes and also practice using GET routes and POST routes.

```
const students = [
    {
      id: 1,
      last: "Last1",
      first: "First1",
    },
    {
      id: 2,
      last: "Last2",
      first: "First2",
    },
    {
      id: 3,
      last: "Last3",
      first: "First3",
    }
  ];

const fastify = require("fastify")();

fastify.get("/cit/student", (request, reply) => {
    reply
        .code(200)
        .header("Content-Type", "text/html")
        .send(`<h1> ${students[0].first} ${students[0].last} ${students[1].first} ${students[1].last} ${students[2].first} ${students[2].last}</h1>`);
})

fastify.get("/cit/student/:id", (request, reply) => {
    const {id} = request.params;
    const {first, last} = request.body;
    for (const object of students) {

    }
})

fastify.get("*", (request, reply) => {
    reply
        .code(404)
        .header("Content-Type", "text/html; charset=utf-8")
        .send("<h1>Unsupported request or page!</h1>");
})

const listenIP = "localhost";
const listenPort = 8080;

fastify.listen(listenPort, listenIP, (err, address) => {
    if (err) {
      console.log(err);
      process.exit(1);
    }
    console.log(`Server listening on ${address}`);
  });
```
<img width="594" alt="AllStudents" src="https://user-images.githubusercontent.com/105889862/172033463-4e091197-fa34-461e-b431-a8187981181d.png">

