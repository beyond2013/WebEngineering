# 🛠️ Instructor’s Note on AI & Ethics
> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI, Google Gemini) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.
---
# Week 7: JavaScript Basics
---

# Learning Outcomes

By the end of this lecture, students will be able to:

* Explain the role of JavaScript in web development
* Differentiate between HTML, CSS, and JavaScript
* Declare and use variables in JavaScript
* Work with basic data types and operators
* Create and call functions
* Handle basic events such as button clicks
* Add simple interactivity to webpages

---


# Introduction to JavaScript

## What is JavaScript?

JavaScript is a **programming language** used to make webpages interactive and dynamic.

It allows webpages to:

* Respond to user actions
* Validate forms
* Display animations
* Update content dynamically
* Create interactive applications

---

# HTML, CSS, and JavaScript Together

| Technology | Purpose                    |
| ---------- | -------------------------- |
| HTML       | Structure of webpage       |
| CSS        | Styling and layout         |
| JavaScript | Behavior and interactivity |

### Analogy

| Part       | Example             |
| ---------- | ------------------- |
| HTML       | Skeleton            |
| CSS        | Clothing/appearance |
| JavaScript | Brain and movement  |

---

# Role of JavaScript in Web Development

JavaScript is used for:

* Button interactions
* Pop-up messages
* Form validation
* Dynamic menus
* Image sliders
* Games and animations
* Real-time updates
* Web applications

---

# Ways to Add JavaScript

## 1. Inline JavaScript

```html
<button onclick="alert('Hello!')">Click Me</button>
```

---

## 2. Internal JavaScript

```html
<script>
    alert("Welcome");
</script>
```

---

## 3. External JavaScript

### HTML File

```html
<script src="script.js"></script>
```

### JavaScript File

```javascript
alert("External JavaScript");
```

---

# JavaScript Syntax Basics

## Important Rules

* JavaScript statements end with semicolons `;`
* It is case-sensitive
* Comments improve readability

---

## Single-Line Comment

```javascript
// This is a comment
```

---

## Multi-Line Comment

```javascript
/*
This is
a multi-line comment
*/
```

---

# Variables in JavaScript

## What is a Variable?

A variable stores data.

---

## Declaring Variables

```javascript
let name = "Ali";
let age = 20;
```

---

## Variable Keywords

| Keyword | Description                 |
| ------- | --------------------------- |
| let     | Modern variable declaration |
| const   | Constant value              |
| var     | Older method                |

---

# Naming Rules for Variables

## Allowed

```javascript
let studentName;
let marks1;
```

## Not Allowed

```javascript
let 1name;
let student-name;
```

---

# Data Types in JavaScript

## Common Data Types

| Data Type | Example     |
| --------- | ----------- |
| String    | `"Hello"`   |
| Number    | `25`        |
| Boolean   | `true`      |
| Null      | `null`      |
| Undefined | `undefined` |

---

## Example

```javascript
let name = "Imran";
let age = 30;
let isTeacher = true;
```

---

# Output in JavaScript

## Using alert()

```javascript
alert("Welcome to JavaScript");
```

---

## Using console.log()

```javascript
console.log("Debug message");
```

Explain that `console.log()` output appears in the browser console.

---

# Operators in JavaScript

## Arithmetic Operators

| Operator | Meaning        |
| -------- | -------------- |
| +        | Addition       |
| -        | Subtraction    |
| *        | Multiplication |
| /        | Division       |
| %        | Modulus        |

---

## Example

```javascript
let a = 10;
let b = 5;

console.log(a + b);
console.log(a - b);
console.log(a * b);
```

---

# Assignment Operators

| Operator | Example |
| -------- | ------- |
| =        | x = 5   |
| +=       | x += 2  |
| -=       | x -= 1  |

---

# Comparison Operators

| Operator | Meaning      |
| -------- | ------------ |
| ==       | Equal        |
| ===      | Strict equal |
| !=       | Not equal    |
| >        | Greater than |
| <        | Less than    |

---

# Logical Operators

| Operator | Meaning |
| -------- | ------- |
| &&       | AND     |
| ||       | OR      |
| !        | NOT     |

---

# Functions in JavaScript

## What is a Function?

A function is a reusable block of code.

---

## Function Syntax

```javascript
function greet() {
    alert("Hello Students");
}
```

---

## Calling a Function

```javascript
greet();
```

---

# Function with Parameters

```javascript
function add(a, b) {
    return a + b;
}

let result = add(5, 3);

console.log(result);
```

---

# Events in JavaScript

## What is an Event?

An event is an action performed by the user or browser.

Examples:

* Mouse click
* Key press
* Page load
* Mouse hover

---

# onclick Event Example

```html
<button onclick="showMessage()">Click Me</button>

<script>
function showMessage() {
    alert("Button Clicked");
}
</script>
```

---

# Changing HTML Content with JavaScript

## Example

```html
<p id="demo">Original Text</p>

<button onclick="changeText()">Change Text</button>

<script>
function changeText() {
    document.getElementById("demo").innerHTML = "Text Changed!";
}
</script>
```

---

# JavaScript and the DOM

## DOM (Document Object Model)

JavaScript can access and modify HTML elements using the DOM.

Examples:

* Change text
* Change styles
* Hide/show elements
* Respond to events

---

# Example: Change Background Color

```html
<button onclick="changeColor()">Change Background</button>

<script>
function changeColor() {
    document.body.style.backgroundColor = "lightblue";
}
</script>
```

---

# Common JavaScript Errors

| Error               | Cause             |
| ------------------- | ----------------- |
| Missing quotes      | Incorrect string  |
| Misspelled variable | Case sensitivity  |
| Missing brackets    | Syntax issue      |
| Wrong element ID    | Element not found |

---

# Debugging Tips

* Use browser console
* Read error messages carefully
* Test small portions of code
* Check spelling and syntax

---

# Practical Demonstration

During class, demonstrate:

1. Adding a button
2. Showing an alert message
3. Changing webpage text
4. Changing background color
5. Creating and calling functions

---

# Lab Activity

# Lab: Add Interactivity Using JavaScript

## Objective

Create a webpage with interactive JavaScript features.

---

# Requirements

Students should create a webpage containing:

* A heading
* A paragraph
* At least two buttons

---

# Functionalities

## Button 1

Display an alert message.

Example:

```javascript
alert("Welcome Student");
```

---

## Button 2

Change the text of a paragraph.

Example:

```javascript
document.getElementById("demo").innerHTML = "New Text";
```

---

# Bonus Tasks

Advanced students may additionally:

* Change background color
* Display current date/time
* Create a simple calculator
* Ask user input using `prompt()`

---

# Complete Lab Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Basics</title>
</head>
<body>

    <h1>JavaScript Demo</h1>

    <p id="demo">This is original text.</p>

    <button onclick="showAlert()">Show Alert</button>

    <button onclick="changeText()">Change Text</button>

    <script>

        function showAlert() {
            alert("Welcome to JavaScript");
        }

        function changeText() {
            document.getElementById("demo").innerHTML =
                "The text has been changed!";
        }

    </script>

</body>
</html>
```

---

# In-Class Discussion Questions

1. Why is JavaScript important in modern websites?
2. What is the difference between HTML, CSS, and JavaScript?
3. What is a function?
4. What is an event?
5. What happens when a button is clicked?

---

# Summary

In this lecture, students learned:

* The purpose of JavaScript
* How JavaScript adds interactivity
* Variables and data types
* Operators
* Functions
* Events and button clicks
* DOM manipulation basics

---

# Preparation for Next Lecture

Next week students will learn:

* Conditional statements (`if`, `else`)
* Loops
* Arrays
* More DOM manipulation
* Simple interactive projects
