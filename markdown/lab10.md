# 💡 Lab Activity: Refactoring a Poorly Designed Client-Side Application

## Objective

In real-world projects, web applications often become difficult to maintain because HTML, CSS, and JavaScript are mixed together in a single file with poor organization and naming conventions.

Your task is to transform the following poorly designed application into a well-structured, maintainable, and professional project by applying the principles of **Separation of Concerns** and **Code Organization**.

---

## Starter Code (Messy Version)

Save the following code as `index.html`.

```html
<!DOCTYPE html>
<html>
<head>
<title>Student Portal</title>

<style>

body{font-family:arial;background:#ddd;margin:0;padding:0}

h1{background:blue;color:white;padding:10px}

input{padding:5px;margin:2px}

button{padding:5px;background:green;color:white;border:none}

table{width:100%;margin-top:20px;border-collapse:collapse}

td,th{border:1px solid black;padding:5px}

.red{color:red}

.big{font-size:20px}

</style>

</head>

<body>

<h1>Student Portal</h1>

<div>

<input id="n" placeholder="Name">

<input id="a" placeholder="Age">

<button onclick="add()">Add Student</button>

<button onclick="clearData()">Clear Form</button>

</div>

<br>

<input id="search" placeholder="Search Student" onkeyup="searchStudent()">

<p id="count" class="big">Students: 0</p>

<table id="t">

<tr>
<th>Name</th>
<th>Age</th>
<th>Action</th>
</tr>

</table>

</body>

<script>

var total=0

function add(){

var name=document.getElementById("n").value
var age=document.getElementById("a").value

if(name==""||age==""){
alert("Fill all fields")
return
}

var table=document.getElementById("t")

var row=table.insertRow(-1)

var c1=row.insertCell(0)
var c2=row.insertCell(1)
var c3=row.insertCell(2)

c1.innerHTML=name
c2.innerHTML=age

c3.innerHTML="<button onclick='del(this)'>Delete</button>"

total++

document.getElementById("count").innerHTML="Students: "+total

document.getElementById("n").value=""
document.getElementById("a").value=""

}

function del(btn){

if(confirm("Delete student?")){

btn.parentNode.parentNode.remove()

total--

document.getElementById("count").innerHTML="Students: "+total

}

}

function clearData(){

document.getElementById("n").value=""
document.getElementById("a").value=""

}

function searchStudent(){

var filter=document.getElementById("search").value.toUpperCase()

var table=document.getElementById("t")

var tr=table.getElementsByTagName("tr")

for(var i=1;i<tr.length;i++){

var td=tr[i].getElementsByTagName("td")[0]

if(td){

var txt=td.textContent||td.innerText

if(txt.toUpperCase().indexOf(filter)>-1){

tr[i].style.display=""

}else{

tr[i].style.display="none"

}

}

}

}

</script>

</html>
```

---

# Tasks

## Part 1: Code Review

Carefully examine the code and identify at least **five problems** related to:

- Readability
- Maintainability
- Code organization
- Naming conventions
- Separation of concerns

Document your observations.

---

## Part 2: Apply Separation of Concerns

Create the following project structure:

```text
student-portal/
│
├── index.html
├── css/
│   └── style.css
│
├── js/
│   └── app.js
│
└── README.txt
```

Move:

- HTML code into `index.html`
- CSS code into `css/style.css`
- JavaScript code into `js/app.js`

Link the files correctly.

---

## Part 3: Improve Code Organization

Refactor the application by:

### HTML

- Use meaningful IDs and class names.
- Add comments for major sections.
- Improve indentation and formatting.
- Use semantic elements where appropriate.

### CSS

Organize styles into logical sections:

```css
/* General Styles */

/* Form Styles */

/* Table Styles */

/* Utility Classes */
```

Remove redundant styles and improve readability.

### JavaScript

Replace cryptic variable names with meaningful names.

Example:

```javascript
// Bad
var n
var a
var t

// Better
const studentName
const studentAge
const studentTable
```

Group related functions together.

Example:

```javascript
// Form Functions

// Table Functions

// Search Functions
```

---

## Part 4: Remove Inline Event Handlers

Replace all inline handlers such as:

```html
<button onclick="add()">
```

and

```html
<input onkeyup="searchStudent()">
```

with JavaScript event listeners.

Example:

```javascript
button.addEventListener("click", addStudent);
```

---

## Part 5: Add New Features

Implement **at least THREE** of the following enhancements:

### Option A: Form Validation

- Name cannot be empty.
- Age must be numeric.
- Display validation messages.

### Option B: Dark Mode

Add a button that switches between light and dark themes.

### Option C: Student Search Improvements

Make searching case-insensitive and user-friendly.

### Option D: Sort Students

Add a button to sort students alphabetically.

### Option E: Student Statistics

Display:

- Total students
- Average age

### Option F: Responsive Design

Ensure the page displays properly on mobile devices.

### Option G: Confirmation Messages

Provide user feedback when records are added or deleted.

---

## Part 6: Documentation

Create a file named:

```text
README.txt
```

Include:

1. Problems found in the original code.
2. Improvements made.
3. Features added.
4. Project structure explanation.

---

# Deliverables

Submit a ZIP file containing:

```text
student-portal.zip
│
├── index.html
├── css/
│   └── style.css
│
├── js/
│   └── app.js
│
└── README.txt
```

---

# Learning Outcomes

By completing this activity, students will be able to:

- Apply Separation of Concerns.
- Organize client-side code professionally.
- Improve readability and maintainability.
- Refactor poorly structured code.
- Use event listeners instead of inline handlers.
- Create responsive and user-friendly web applications.
- Understand why modern frameworks encourage modular design.

---

# Estimated Time

| Activity | Duration |
|-----------|----------|
| Code Review | 15 min |
| File Separation | 20 min |
| Refactoring | 30 min |
| Feature Development | 40 min |
| Documentation | 15 min |
| **Total** | **120 min** |