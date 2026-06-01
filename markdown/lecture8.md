# 🛠️ Instructor’s Note on AI & Ethics
> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.

---

# Week 8: JavaScript & DOM Manipulation

## Learning Outcomes

By the end of this lecture, students will be able to:

- Understand the Document Object Model (DOM).
- Access and manipulate HTML elements using JavaScript.
- Modify content, styles, and attributes dynamically.
- Handle user-generated events such as clicks and keyboard input.
- Create basic client-side form validation.
- Develop interactive web pages using DOM manipulation techniques.

---

# Recap of Previous Lecture (Week 7: JavaScript Basics)

In the previous lecture, we learned:

- The role of JavaScript in web development.
- How JavaScript is included in web pages.
- Variables (`let`, `const`, `var`).
- Data types (String, Number, Boolean, etc.).
- Operators and expressions.
- Functions.
- Events such as button clicks.
- Creating simple interactive pages using alerts and event handlers.

Example:

```javascript
function greet() {
    alert("Welcome to Web Engineering!");
}
```

---

# Introduction to the DOM

When a web page loads, the browser converts the HTML document into a structured object called the **Document Object Model (DOM)**.

The DOM represents the webpage as a tree of objects that JavaScript can access and manipulate.

HTML:

```html
<body>
    <h1>Welcome</h1>
    <p>This is a paragraph.</p>
</body>
```

DOM Tree:

```text
Document
 |
 └── html
      |
      ├── head
      |
      └── body
            |
            ├── h1
            |
            └── p
```

JavaScript can:

- Read elements
- Change content
- Modify styles
- Add or remove elements
- Respond to user actions

This is what makes web pages interactive.

---

# Why DOM Manipulation is Important

Without DOM manipulation:

- Web pages remain static.
- User interaction is limited.

With DOM manipulation:

- Content updates without reloading the page.
- Forms can be validated instantly.
- Interactive menus can be created.
- Dynamic interfaces become possible.

Examples:

- Live search suggestions
- Form validation
- Image sliders
- Shopping carts
- Interactive dashboards

---

# Accessing DOM Elements

Before modifying an element, JavaScript must first locate it.

## 1. Selecting by ID

HTML:

```html
<h1 id="title">Hello World</h1>
```

JavaScript:

```javascript
let heading = document.getElementById("title");

console.log(heading);
```

---

## 2. Selecting by Class

HTML:

```html
<p class="message">First</p>
<p class="message">Second</p>
```

JavaScript:

```javascript
let paragraphs =
    document.getElementsByClassName("message");

console.log(paragraphs);
```

Returns a collection of matching elements.

---

## 3. Selecting by Tag Name

```javascript
let paragraphs =
    document.getElementsByTagName("p");
```

Returns all paragraph elements.

---

## 4. Modern Selectors

### querySelector()

Returns the first matching element.

```javascript
let heading =
    document.querySelector("#title");
```

### querySelectorAll()

Returns all matching elements.

```javascript
let items =
    document.querySelectorAll(".message");
```

---

# Modifying Content

JavaScript can change text displayed on the page.

HTML:

```html
<h2 id="heading">
    Original Text
</h2>
```

JavaScript:

```javascript
document.getElementById("heading")
        .innerHTML =
        "Updated Text";
```

Output:

```text
Original Text
```

becomes

```text
Updated Text
```

---

# Changing HTML Content

HTML:

```html
<div id="content"></div>
```

JavaScript:

```javascript
document.getElementById("content")
        .innerHTML =
        "<h3>Welcome Student</h3>";
```

The HTML is rendered dynamically.

---

# Modifying Styles

JavaScript can change CSS properties.

HTML:

```html
<p id="text">Sample Text</p>
```

JavaScript:

```javascript
let para =
    document.getElementById("text");

para.style.color = "red";
para.style.fontSize = "24px";
```

Result:

- Text becomes red.
- Font size increases.

---

# Changing Attributes

HTML:

```html
<img id="logo"
     src="old.png">
```

JavaScript:

```javascript
document.getElementById("logo")
        .src = "new.png";
```

The displayed image changes immediately.

---

# Creating and Removing Elements

## Creating Elements

```javascript
let para =
    document.createElement("p");

para.innerHTML =
    "This paragraph was created dynamically.";

document.body.appendChild(para);
```

---

## Removing Elements

```javascript
let element =
    document.getElementById("oldElement");

element.remove();
```

---

# Introduction to Events

An **event** is an action performed by the user or browser.

Examples:

| Event | Description |
|---------|-------------|
| click | User clicks |
| dblclick | Double click |
| keyup | Key released |
| keydown | Key pressed |
| submit | Form submitted |
| change | Input value changed |
| mouseover | Mouse enters element |

---

# Event Handling

JavaScript can respond to events.

HTML:

```html
<button onclick="showMessage()">
    Click Me
</button>
```

JavaScript:

```javascript
function showMessage() {
    alert("Button Clicked!");
}
```

---

# Using addEventListener()

Modern JavaScript uses `addEventListener()`.

HTML:

```html
<button id="btn">
    Click Me
</button>
```

JavaScript:

```javascript
let button =
    document.getElementById("btn");

button.addEventListener(
    "click",
    function() {
        alert("Button Pressed");
    }
);
```

Advantages:

- Cleaner code
- Multiple handlers possible
- Better maintainability

---

# Example: Changing Text on Button Click

HTML:

```html
<h2 id="heading">
    Welcome
</h2>

<button id="changeBtn">
    Change Text
</button>
```

JavaScript:

```javascript
let button =
    document.getElementById("changeBtn");

button.addEventListener(
    "click",
    function() {
        document.getElementById("heading")
                .innerHTML =
                "Text Updated!";
    }
);
```

---

# Example: Live Character Counter

HTML:

```html
<textarea id="message"></textarea>

<p id="count">
    Characters: 0
</p>
```

JavaScript:

```javascript
let textBox =
    document.getElementById("message");

textBox.addEventListener(
    "keyup",
    function() {

        let length =
            textBox.value.length;

        document.getElementById("count")
                .innerHTML =
                "Characters: " + length;
    }
);
```

This updates the count while the user types.

---

# Form Validation

Validation ensures that users enter correct data before submission.

Common validations:

- Required fields
- Email format
- Password length
- Numeric input
- Range checking

Benefits:

- Improved user experience
- Reduced server-side errors
- Better data quality

---

# Basic Form Validation Example

HTML:

```html
<form onsubmit="return validateForm()">

    Name:
    <input type="text" id="name">

    <input type="submit"
           value="Submit">

</form>
```

JavaScript:

```javascript
function validateForm() {

    let name =
        document.getElementById("name").value;

    if (name === "") {

        alert("Name is required");

        return false;
    }

    return true;
}
```

If the field is empty, submission is blocked.

---

# Email Validation Example

HTML:

```html
<input type="text"
       id="email">
```

JavaScript:

```javascript
function validateEmail() {

    let email =
        document.getElementById("email").value;

    if (!email.includes("@")) {

        alert("Invalid Email");

        return false;
    }

    return true;
}
```

---

# Complete Example

HTML:

```html
<form id="studentForm">

    Name:
    <input type="text" id="name">
    <br><br>

    Email:
    <input type="text" id="email">
    <br><br>

    <button type="submit">
        Submit
    </button>

</form>
```

JavaScript:

```javascript
document.getElementById("studentForm")
        .addEventListener(
            "submit",
            function(event) {

                let name =
                    document.getElementById("name").value;

                let email =
                    document.getElementById("email").value;

                if (name === "" ||
                    email === "") {

                    alert(
                        "All fields are required"
                    );

                    event.preventDefault();
                }
            }
        );
```

---

# Best Practices

✔ Use meaningful IDs and class names.

✔ Prefer `addEventListener()` over inline event handlers.

✔ Validate input before processing.

✔ Keep JavaScript in separate files.

✔ Avoid excessive DOM manipulation inside loops.

✔ Write clear and readable code.

---

# Common Mistakes

❌ Using incorrect element IDs.

```javascript
document.getElementById("wrongID");
```

❌ Forgetting to load JavaScript after HTML elements.

❌ Using `=` instead of `==` or `===`.

❌ Not preventing form submission during validation.

❌ Modifying elements that do not exist.

---

# Summary

Today we learned:

- What the DOM is.
- DOM tree structure.
- Selecting HTML elements.
- Modifying content and styles.
- Creating and removing elements.
- Event handling.
- Using `addEventListener()`.
- Client-side form validation.
- Building dynamic and interactive web pages.

---

# Lab Activity: Dynamic Form Validation

## Objective

Create a student registration form that validates user input before submission.

---

## Requirements

Create a form containing:

1. Student Name
2. Email Address
3. Password
4. Confirm Password
5. Submit Button

---

## Validation Rules

### Name

- Cannot be empty.

### Email

- Must contain `@`.

### Password

- Minimum 8 characters.

### Confirm Password

- Must match Password.

---

## Additional Challenge

Display error messages directly below the corresponding fields instead of using alert boxes.

Example:

```text
Name: [_______]
Name is required

Email: [_______]
Invalid email address
```

---

## Expected Learning Outcomes

After completing the lab, students should be able to:

- Access form elements through the DOM.
- Handle form submission events.
- Validate user input dynamically.
- Prevent invalid form submission.
- Display feedback messages to users.
- Build interactive client-side web applications.