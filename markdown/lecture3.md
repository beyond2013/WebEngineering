# 🛠️ Instructor’s Note on AI & Ethics
> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.

---

# **📘 Lecture 3: HTML Fundamentals – Structure of the Web**

## **🎯 Learning Objectives**

By the end of this lecture, students should be able to:

* Understand what HTML is and why it is used
* Identify the structure of a basic HTML document
* Differentiate between tags, elements, and attributes
* Create a simple webpage using core HTML elements

---

## **1. 🌐 What is HTML?**

**HTML (HyperText Markup Language)** is:

* Not a programming language
* A **markup language** used to structure content on the web

👉 Think of HTML as:

> The **skeleton** of a webpage (structure), while CSS is the skin (appearance) and JavaScript is the brain (behavior)

---

## **2. 🧱 Basic Structure of an HTML Document**

Every webpage follows a standard structure:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Page</title>
</head>
<body>
    <h1>Hello World</h1>
    <p>This is my first webpage.</p>
</body>
</html>
```

### **Explanation**

* `<!DOCTYPE html>` → Declares HTML5 document
* `<html>` → Root element
* `<head>` → Metadata (not visible on page)
* `<title>` → Title shown on browser tab
* `<body>` → Visible content

👉 **Teaching Tip:** Ask students to identify what part will actually appear in the browser.

---

## **3. 🔖 Tags, Elements, and Attributes**

### **Tag**

A tag is a keyword enclosed in angle brackets:

```html
<p>
```

### **Element**

An element includes opening tag, content, and closing tag:

```html
<p>This is a paragraph</p>
```

### **Attribute**

Provides additional information:

```html
<a href="https://google.com">Visit Google</a>
```

👉 `href` is an attribute of the `<a>` tag

---

## **4. 🧾 Common HTML Elements**

### **Headings**

```html
<h1>Main Heading</h1>
<h2>Sub Heading</h2>
<h3>Smaller Heading</h3>
```

👉 There are 6 levels: `<h1>` to `<h6>`

---

### **Paragraph**

```html
<p>This is a paragraph.</p>
```

---

### **Links**

```html
<a href="https://www.example.com">Click here</a>
```

👉 Opens another webpage

---

### **Images**

```html
<img src="image.jpg" alt="Description of image">
```

👉 Note: `<img>` has **no closing tag**

---

## **5. ⚠️ Important Concepts**

### **Nested Elements**

```html
<p>This is a <b>bold</b> word.</p>
```

👉 Elements can be inside other elements

---

### **Empty Elements**

```html
<br>
<hr>
<img>
```

👉 These do not require closing tags

---

### **Case Sensitivity**

* HTML is **not case-sensitive**, but use lowercase (best practice)

---

## **6. 🧪 Live Coding Example**

Ask students to type this:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Page</title>
</head>
<body>
    <h1>Imran's Class</h1>
    <p>Welcome to Web Engineering.</p>
    
    <h2>About Me</h2>
    <p>I am learning HTML.</p>

    <a href="https://www.google.com">Go to Google</a>
</body>
</html>
```

👉 Encourage them to:

* Save as `.html`
* Open in browser
* Modify text and observe changes

---

## **7. 🧠 Conceptual Insight (Very Important)**

Students often think:

> “HTML creates websites”

Correct this early:

> HTML does **not create functionality** — it only defines **structure and meaning**

Example:

* `<h1>` → defines importance, not just size
* `<p>` → defines a paragraph, not just text

---

## **8. ⚡ Mini Activity (In-Class)**

**Task:**
Create a webpage that contains:

* Your name as a heading
* A short introduction paragraph
* A link to your favorite website

👉 This reinforces:

* Structure
* Tags
* Attributes

---

## **9. ❓ Common Mistakes**

* Forgetting closing tags
* Incorrect nesting

```html
<p><b>Wrong</p></b>
```

* Using HTML for styling (instead of CSS)

---

## **10. 🏁 Summary**

* HTML is the **foundation of all web pages**
* It provides **structure, not behavior**
* Core building blocks:

  * Tags
  * Elements
  * Attributes
* A webpage is simply a structured document interpreted by a browser

---

## **📌 Homework**

* Create a personal webpage with:

  * At least 3 headings
  * 2 paragraphs
  * 1 image
  * 2 links

---
