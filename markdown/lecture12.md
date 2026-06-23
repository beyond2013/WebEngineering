# 🛠️ Instructor’s Note on AI & Ethics
> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.

---

# Week 12: Working with Data

## Learning Outcomes

By the end of this lecture, students will be able to:

- Understand how websites collect and process user data.
- Explain the purpose of HTML forms.
- Differentiate between GET and POST methods.
- Understand the basics of JSON.
- Describe the role of databases in web applications.
- Create a simple form that submits and displays data.

---

# 1. Introduction

Most modern websites interact with users by collecting, storing, and processing data.

Examples:

- Login forms
- Registration forms
- Search boxes
- Online shopping carts
- Feedback forms

The process generally follows these steps:

1. User enters data into a form.
2. Browser sends the data to a server.
3. Server processes the data.
4. Server returns a response.
5. Data may be stored in a database.

---

# 2. HTML Forms

HTML forms are used to collect input from users.

## Basic Form Structure

```html
<form>
    <!-- form controls go here -->
</form>
```

Common form controls:

| Element | Purpose |
|----------|----------|
| input | Single-line input |
| textarea | Multi-line text |
| select | Dropdown list |
| checkbox | Multiple selections |
| radio | Single selection |
| button | Submit form |

---

## Example Form

```html
<form>
    Name:
    <input type="text">

    <br><br>

    Email:
    <input type="email">

    <br><br>

    <button type="submit">
        Submit
    </button>
</form>
```

Output:

- Text field for name
- Email field
- Submit button

---

# 3. Form Attributes

## action

Specifies where form data should be sent.

```html
<form action="/submit">
```

Example:

```html
<form action="process.php">
```

The browser sends form data to:

```
process.php
```

---

## method

Specifies how data is sent.

```html
<form action="/submit" method="get">
```

or

```html
<form action="/submit" method="post">
```

Two common methods:

- GET
- POST

---

# 4. GET Method

GET sends data through the URL.

Example:

```html
<form action="/search" method="get">
```

User enters:

```
Laptop
```

Generated URL:

```
/search?item=Laptop
```

Example URL:

```
https://example.com/search?item=Laptop
```

---

## Advantages of GET

- Easy to test
- Bookmarkable
- Useful for searches
- Data visible in URL

---

## Disadvantages of GET

- Limited amount of data
- Not suitable for passwords
- Data visible to everyone

---

## Typical Uses

- Search forms
- Filters
- Public information requests

Example:

```
Google Search
```

---

# 5. POST Method

POST sends data inside the HTTP request body.

Example:

```html
<form action="/register" method="post">
```

URL remains:

```
https://example.com/register
```

Data is not displayed in the URL.

---

## Advantages of POST

- More secure than GET
- Supports larger data
- Suitable for sensitive information

---

## Disadvantages of POST

- Cannot easily bookmark submissions
- Slightly harder to test manually

---

## Typical Uses

- Login forms
- Registration forms
- Online orders
- File uploads

---

# 6. GET vs POST

| Feature | GET | POST |
|----------|----------|----------|
| Data Location | URL | Request Body |
| Visible to User | Yes | No |
| Bookmarkable | Yes | No |
| Suitable for Passwords | No | Better |
| Data Size | Limited | Larger |
| Typical Use | Search | Form Submission |

---

# 7. Introduction to JSON

JSON stands for:

**JavaScript Object Notation**

JSON is a lightweight format used to exchange data between systems.

Today it is the most common data format used in web applications and APIs.

---

## JSON Example

```json
{
    "name": "Ali",
    "age": 20,
    "city": "Quetta"
}
```

---

## JSON Rules

### Data is stored as key-value pairs

```json
{
    "name": "Ali"
}
```

Key:

```json
"name"
```

Value:

```json
"Ali"
```

---

### Strings use double quotes

Correct:

```json
{
    "name": "Ali"
}
```

Incorrect:

```json
{
    'name': 'Ali'
}
```

---

### Multiple Values

```json
{
    "name": "Ali",
    "age": 20,
    "city": "Quetta"
}
```

---

## JSON Array

```json
{
    "courses": [
        "Web Engineering",
        "Database Systems",
        "Programming Fundamentals"
    ]
}
```

---

# 8. Why JSON is Important

JSON is used when:

- Browser communicates with server
- Mobile apps communicate with servers
- APIs exchange information
- Data is transferred between systems

Example response from a server:

```json
{
    "studentId": 101,
    "name": "Ali",
    "cgpa": 3.45
}
```

---

# 9. Introduction to Databases

A database is an organized collection of data.

Instead of storing information in separate files, web applications typically store data in databases.

Examples:

- Student records
- Employee records
- Product catalogs
- Banking systems

---

## Real World Example

University database may store:

| Student ID | Name | Program |
|------------|--------|----------|
| 101 | Ali | BSCS |
| 102 | Sara | BSIT |
| 103 | Ahmed | BSSE |

---

# 10. Why Databases Are Needed

Without databases:

- Data becomes difficult to manage
- Searching becomes slow
- Updates become difficult
- Duplicate records may occur

Databases provide:

- Storage
- Searching
- Updating
- Security
- Backup

---

# 11. Database Terminology (High Level)

## Table

A collection of related records.

Example:

```
Students
```

---

## Record (Row)

One complete entry.

Example:

| Student ID | Name |
|------------|--------|
| 101 | Ali |

This row is one record.

---

## Field (Column)

Individual data items.

Example:

| Student ID | Name | Program |
|------------|--------|----------|

Student ID, Name, and Program are fields.

---

# 12. How Forms, Servers, and Databases Work Together

Example: Student Registration

Step 1:

Student fills form.

```
Name: Ali
Program: BSCS
```

Step 2:

Browser sends data to server.

Step 3:

Server validates data.

Step 4:

Server stores data in database.

Step 5:

Server sends confirmation message.

```
Registration Successful
```

---

# Data Flow Diagram

```text
User
  |
  v
HTML Form
  |
  v
Server
  |
  v
Database
  |
  v
Response Back to User
```

---

# Lab: Submit and Display Form Data

## Objective

Create a simple web application where:

1. User enters information.
2. Form data is submitted.
3. Server receives the data.
4. Server displays the submitted values.

---

## Step 1: Create HTML Form

File: `index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Form</title>
</head>
<body>

    <h2>Student Information Form</h2>

    <form action="/submit" method="post">

        Name:
        <input type="text" name="name">

        <br><br>

        Program:
        <input type="text" name="program">

        <br><br>

        <button type="submit">
            Submit
        </button>

    </form>

</body>
</html>
```

---

## Step 2: Create Node.js Server

File: `server.js`

```javascript
const http = require('http');
const querystring = require('querystring');

const server = http.createServer((req, res) => {

    if (req.method === 'POST' && req.url === '/submit') {

        let body = '';

        req.on('data', chunk => {
            body += chunk;
        });

        req.on('end', () => {

            const data = querystring.parse(body);

            res.writeHead(200, {
                'Content-Type': 'text/html'
            });

            res.end(`
                <h2>Submitted Data</h2>
                <p>Name: ${data.name}</p>
                <p>Program: ${data.program}</p>
            `);
        });

    } else {

        res.writeHead(200, {
            'Content-Type': 'text/html'
        });

        res.end(`
            <h2>Open index.html in browser</h2>
        `);
    }
});

server.listen(3000, () => {
    console.log('Server running on port 3000');
});
```

---

## Running the Lab

Open terminal:

```bash
node server.js
```

Output:

```text
Server running on port 3000
```

Open:

```text
http://localhost:3000
```

Submit the form and observe the displayed data.

---

# Summary

In this lecture, we learned:

- HTML forms collect user input.
- Forms use GET or POST methods.
- GET places data in the URL.
- POST sends data in the request body.
- JSON is a popular data exchange format.
- Databases store and manage application data.
- Web applications often follow the flow:

```text
User -> Form -> Server -> Database -> Response
```

This completes the basic data-handling concepts required before moving toward more advanced server-side web development.
