# 🛠️ Instructor’s Note on AI & Ethics
> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.

---

# Week 11: Server-Side Basics

## Learning Outcomes

By the end of this lecture, students will be able to:

- Explain the role of server-side programming in web applications.
- Understand how client requests are processed by a web server.
- Differentiate between static and dynamic web pages.
- Understand the basic concepts of Node.js.
- Create a simple server that returns an HTML page.

---

# 1. Introduction

So far, we have focused on technologies that run inside the user's browser:

- HTML → Structure
- CSS → Presentation
- JavaScript → Client-side interactivity

These technologies are known as **client-side technologies** because they execute on the user's computer.

However, many modern websites need functionality such as:

- User login
- Online shopping
- Database access
- Processing forms
- Personalized content

These tasks cannot be performed securely using only client-side code.

For this purpose, we use **server-side programming**.

---

# 2. What is Server-Side Programming?

Server-side programming refers to code that runs on a web server rather than inside the user's browser.

The server receives requests from clients, processes them, and sends back responses.

## Examples

When a user:

- Logs into Facebook
- Searches on Google
- Checks email
- Books a ticket online

The processing happens on the server.

---

## Client-Side vs Server-Side

| Client-Side | Server-Side |
|------------|-------------|
| Runs in browser | Runs on server |
| HTML, CSS, JavaScript | Node.js, PHP, Python, Java, etc. |
| Handles UI and interaction | Handles business logic and data |
| Visible to user | Hidden from user |
| Limited access to server resources | Can access databases and files |

---

# 3. Web Application Architecture

A typical web application consists of three components:

## Client

The user's browser.

Examples:

- Chrome
- Firefox
- Edge

## Server

Processes requests and generates responses.

Examples:

- Node.js Server
- Apache Server
- Nginx Server

## Database

Stores data permanently.

Examples:

- MySQL
- PostgreSQL
- MongoDB

---

## Simple Architecture Diagram

```
Browser
   |
   | Request
   V
Server
   |
   | Query
   V
Database
   |
   | Data
   V
Server
   |
   | Response
   V
Browser
```

---

# 4. Understanding HTTP Requests

Communication between browser and server occurs through the **HTTP protocol**.

Whenever a user visits a website, the browser sends a request.

Example:

```
https://example.com
```

The browser requests:

```
GET /
```

The server processes the request and returns:

```
HTML Page
```

---

## Common HTTP Methods

### GET

Used to retrieve data.

Example:

```
GET /products
```

Meaning:

"Please send me the products page."

---

### POST

Used to send data to the server.

Example:

```
POST /login
```

Meaning:

"Here are my username and password."

---

# 5. Request Handling Concept

Request handling is the process by which a server receives a request and decides what response to send.

---

## Real-Life Example

Imagine a restaurant.

### Customer

Places an order.

### Waiter

Receives the order.

### Kitchen

Processes the order.

### Waiter

Returns the food.

Similarly:

| Restaurant | Web Application |
|------------|----------------|
| Customer | Browser |
| Waiter | Server |
| Kitchen | Application Logic |
| Food | Response |

---

## Request Handling Flow

```
User clicks a link
        |
        V
Browser sends request
        |
        V
Server receives request
        |
        V
Server processes request
        |
        V
Server generates response
        |
        V
Browser displays response
```

---

# 6. Introduction to Node.js

For this course we will use **Node.js**.

Node.js allows JavaScript to run outside the browser.

Before Node.js:

- JavaScript only worked in browsers.

With Node.js:

- JavaScript can create servers.
- JavaScript can access files.
- JavaScript can communicate with databases.

---

## Why Node.js?

### Advantages

- Uses JavaScript on both client and server.
- Fast execution.
- Large community support.
- Easy to learn for web developers.

---

## Typical Uses

- Web servers
- APIs
- Real-time chat applications
- Streaming services

Examples:

- Netflix
- PayPal
- LinkedIn (parts of their infrastructure)

---

# 7. Static vs Dynamic Pages

One of the most important concepts in server-side development is understanding the difference between static and dynamic content.

---

## Static Pages

A static page always sends the same content.

Example:

```
about.html
```

Every visitor receives exactly the same page.

---

### Characteristics

- Simple
- Fast
- No database required
- Same content for everyone

---

### Example

```
Welcome to our website.
```

Every user sees:

```
Welcome to our website.
```

---

## Dynamic Pages

A dynamic page is generated by the server at runtime.

Content can change depending on:

- User
- Date
- Database data
- Search query
- Login status

---

### Example

User A logs in:

```
Welcome Imran
```

User B logs in:

```
Welcome Ahmed
```

Same URL, different content.

---

### Characteristics

- Personalized
- Interactive
- Can use databases
- Generated when requested

---

## Static vs Dynamic Comparison

| Static Page | Dynamic Page |
|-------------|-------------|
| Fixed content | Generated content |
| Same for everyone | Different for different users |
| No server logic required | Requires server logic |
| Faster | More processing required |
| Usually HTML files | Generated using server-side code |

---

# 8. How Dynamic Content Works

Consider a weather website.

User requests:

```
weather.com
```

Server:

1. Receives request.
2. Retrieves latest weather data.
3. Generates HTML.
4. Sends response.

The page changes every time because the data changes.

---

# 9. Creating a Simple Node.js Server

Node.js provides a built-in module called:

```javascript
http
```

This module can create a web server.

---

## Basic Structure

```javascript
const http = require("http");

const server = http.createServer((req, res) => {
    res.end("Hello World");
});

server.listen(3000);
```

---

## Explanation

### Import HTTP Module

```javascript
const http = require("http");
```

Loads the HTTP functionality.

---

### Create Server

```javascript
http.createServer(...)
```

Creates a server that waits for requests.

---

### Request Object

```javascript
req
```

Contains information about the incoming request.

Examples:

- URL
- Method
- Headers

---

### Response Object

```javascript
res
```

Used to send data back to the browser.

---

### Start Listening

```javascript
server.listen(3000);
```

Server waits for requests on port 3000.

---

# 10. Returning HTML from the Server

Instead of returning plain text, we can return an HTML page.

Example:

```javascript
const http = require("http");

const server = http.createServer((req, res) => {

    res.writeHead(200, {
        "Content-Type": "text/html"
    });

    res.end(`
        <html>
            <body>
                <h1>Welcome to Web Engineering</h1>
                <p>This page was generated by Node.js.</p>
            </body>
        </html>
    `);
});

server.listen(3000);
```

---

## Expected Output

When visiting:

```
http://localhost:3000
```

The browser displays:

# Welcome to Web Engineering

This page was generated by Node.js.

---

# Lab Activity: Simple Server Returning HTML

## Objective

Create a Node.js server that returns a simple HTML webpage.

---

## Requirements

Create a webpage containing:

- Course title
- Student name
- Department name
- A welcome message

---

## Step 1: Create Project Folder

Create a folder:

```
Week11Lab
```

---

## Step 2: Create File

Create:

```
server.js
```

---

## Step 3: Write Code

```javascript
const http = require("http");

const server = http.createServer((req, res) => {

    res.writeHead(200, {
        "Content-Type": "text/html"
    });

    res.end(`
        <!DOCTYPE html>
        <html>
        <head>
            <title>My First Server</title>
        </head>
        <body>
            <h1>Web Engineering Lab</h1>
            <h2>Student Name: Your Name</h2>
            <h3>Department of Computer Science</h3>
            <p>Welcome to server-side programming using Node.js.</p>
        </body>
        </html>
    `);
});

server.listen(3000, () => {
    console.log("Server running at http://localhost:3000");
});
```

---

## Step 4: Run the Server

Open terminal inside the project folder.

Execute:

```bash
node server.js
```

---

## Step 5: Open Browser

Visit:

```
http://localhost:3000
```

---

## Expected Result

The browser should display a webpage generated by the Node.js server containing:

- Heading
- Student information
- Department information
- Welcome message

---

# Summary

In this lecture we learned:

- What server-side programming is.
- The difference between client-side and server-side processing.
- How HTTP requests and responses work.
- The concept of request handling.
- Introduction to Node.js.
- Difference between static and dynamic pages.
- How to create a simple Node.js server.
- How to return HTML content from the server.

Next Week: Introduction to Databases and Server-Side Data Handling.