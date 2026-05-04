# 🛠️ Instructor’s Note on AI & Ethics
> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI, Google Gemini) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.
---

# **Week 5: CSS Basics**

## **1. Introduction to CSS**

CSS (Cascading Style Sheets) controls the **appearance of HTML elements**.

* HTML → structure
* CSS → presentation
* Encourages **separation of concerns**
* Makes websites **consistent and easier to maintain**

---

## **2. Ways to Apply CSS**

### **a) Inline CSS**

Applied directly inside an HTML element.

```html
<p style="color: blue; font-size: 18px;">Hello World</p>
```

**Explanation:**

* `style` attribute contains CSS properties
* Each property is written as `property: value;`

**Best Practice:**

* Avoid in real projects
* Use only for **quick testing or overrides**

---

### **b) Internal CSS**

Defined inside a `<style>` tag within the `<head>` section.

```html
<head>
  <style>
    p {
      color: green;
      font-size: 16px;
    }
  </style>
</head>
```

**Explanation:**

* Targets all `<p>` elements on that page
* Useful when styling **a single HTML file**

**Best Practice:**

* Acceptable for small projects
* Avoid for multi-page websites

---

### **c) External CSS (Recommended)**

Stored in a separate `.css` file.

**HTML file:**

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

**CSS file (styles.css):**

```css
p {
  color: red;
  font-size: 16px;
}
```

**Explanation:**

* CSS is separated from HTML
* One CSS file can style **multiple pages**

**Best Practice:**

* Always prefer external CSS
* Keeps code clean, reusable, and maintainable

---

## **3. CSS Selectors**

Selectors define **which elements** the styles apply to.

### **a) Element Selector**

```css
p {
  color: blue;
}
```

Applies to all `<p>` elements.

---

### **b) ID Selector**

```css
#header {
  color: red;
}
```

```html
<h1 id="header">Welcome</h1>
```

**Explanation:**

* `#` targets a unique element

**Best Practice:**

* Use IDs sparingly
* One ID per page (should be unique)

---

### **c) Class Selector**

```css
.box {
  color: green;
}
```

```html
<div class="box">Content</div>
```

**Explanation:**

* `.` targets reusable styles

**Best Practice:**

* Prefer classes over IDs for styling

---

### **d) Grouping Selector**

```css
h1, h2, p {
  font-family: Arial, Helvetica, sans-serif;
}
```

**Explanation:**

* Applies the same style to multiple elements
* Font list is **comma-separated fallback**

**Important Concept (Font Fallback):**

* Browser tries fonts **left → right**
* If Arial not available → try Helvetica → then any `sans-serif`

**Best Practice:**

* Always end with a **generic family** (`serif`, `sans-serif`, `monospace`)

---

### **e) Descendant Selector**

```css
div p {
  color: purple;
}
```

**Explanation:**

* Targets `<p>` inside `<div>`
* Does NOT affect `<p>` outside `<div>`

---

## **4. Colors in CSS**

### **Different Ways to Define Colors**

```css
p {
  color: red;              /* Named color */
  color: #ff0000;          /* Hex */
  color: rgb(255, 0, 0);   /* RGB */
}
```

**Best Practice:**

* Use **hex or RGB** for precise control
* Keep color scheme consistent

---

## **5. Fonts and Text Styling**

```css
p {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 16px;
  font-weight: 400;   /* 400 = normal, 700 = bold */
  text-align: center;
}
```

**Explanation:**

* `font-family`: fallback system
* `font-size`: controls readability
* `font-weight`: thickness of text

**Best Practice:**

* Use readable sizes (14px–18px for body text)
* Avoid too many different fonts
* Maintain consistency

---

## **6. The Box Model**

Every element is a rectangular box:

```
Margin → Border → Padding → Content
```

### **Example**

```css
div {
  width: 200px;
  padding: 10px;               /* space inside border */
  border: 2px solid black;     /* boundary */
  margin: 20px;                /* space outside */
}
```

**Explanation:**

* `padding` → space between content and border
* `margin` → space between elements

**Best Practice:**

* Use margin for layout spacing
* Use padding for internal spacing
* Avoid random spacing—be consistent

---

## **👉 Lab Activity: Style Previous HTML Pages**

### **Objective**

Apply CSS concepts to improve previously created HTML pages
(e.g., student registration form, profile page, classroom area example)

---

### **Step-by-Step Tasks**

#### **1. Use External CSS**

* Create `style.css`
* Link it properly

```html
<link rel="stylesheet" href="style.css">
```

---

#### **2. Apply Basic Styling**

```css
body {
  background-color: #f4f4f4;
  font-family: Arial, Helvetica, sans-serif;
}
```

---

#### **3. Style Headings and Text**

```css
h1 {
  color: darkblue;
  text-align: center;
}

p {
  color: #333;
}
```

---

#### **4. Use Selectors Properly**

```css
#main-title {
  color: darkgreen;
}

.card {
  border: 1px solid #ccc;
  padding: 10px;
}
```

---

#### **5. Apply Box Model**

```css
.form-container {
  margin: 20px auto;
  padding: 15px;
  width: 300px;
  border: 1px solid black;
}
```

---

#### **6. Improve Form UI**

```css
input {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
}

button {
  background-color: green;
  color: white;
  padding: 10px;
  border: none;
}
```

---

#### **7. Add Hover Effect**

```css
button:hover {
  background-color: darkgreen;
  cursor: pointer;
}
```

**Explanation:**

* `:hover` applies style when mouse is over element

---

## **Expected Output**

* Clean and visually appealing webpage
* Consistent fonts and colors
* Proper spacing using box model

---

## **Extension (For Strong Students)**

* Use `border-radius` for rounded corners
* Add Google Fonts
* Introduce simple transitions:

```css
button {
  transition: background-color 0.3s ease;
}
```

---
