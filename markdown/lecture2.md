# 🛠️ Instructor’s Note on AI & Ethics

> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.

---

# Web Engineering – Lecture 2  
## Web Standards and Their Impact on Development

---

## 🎯 Learning Objectives

By the end of this lecture, students will be able to:

- Understand what **web standards** are  
- Identify key **standardization bodies**  
- Explain why standards are critical  
- Observe how standards affect real code behavior  

---

## 🌐 What Are Web Standards?

Web standards define how web technologies should behave so that applications work consistently across platforms.

---

## ⚠️ Example 1: Non-Standard vs Standard HTML

### ❌ Non-Standard / Bad Practice (Old Web)

    <center>
      <font color="red">Welcome to my website</font>
    </center>

### ✅ Standard-Compliant Approach

    <p class="welcome">Welcome to my website</p>

    .welcome {
      text-align: center;
      color: red;
    }

👉 **Engineering Insight:**
- Old tags (`<font>`, `<center>`) are deprecated  
- Standards enforce **separation of structure and presentation**

---

## ⚠️ Example 2: Browser Inconsistency

### CSS Example

    .box {
      width: 200px;
      padding: 20px;
      border: 5px solid black;
    }

👉 Question:
> What is the total width?

- Some browsers (historically): 200px  
- Standard (CSS Box Model): 250px  

### ✅ Standard Fix

    .box {
      box-sizing: border-box;
    }

👉 **Engineering Insight:**
- Standards remove ambiguity  
- Developers must explicitly control behavior

---

## ⚠️ Example 3: HTML5 Standardization

### Before HTML5 (Plugin Dependency)

    <object data="video.swf"></object>

### After HTML5 (Standard Way)

    <video controls>
      <source src="video.mp4" type="video/mp4">
    </video>

👉 **Engineering Insight:**
- Standards reduce dependency on external plugins  
- Improve security and compatibility

---

## ⚠️ Example 4: JavaScript Compatibility Issues

### Problematic Code

    var element = document.getElementById("demo");
    element.innerText = "Hello";

👉 Issue:
- `innerText` behaves differently across browsers

### Standard Approach

    element.textContent = "Hello";

👉 **Engineering Insight:**
- Prefer **standard APIs** over browser-specific ones

---

## 🧪 Concept: Standard vs Implementation

👉 Even correct code may behave differently:

    input[type="date"] {
      border: 2px solid blue;
    }

- Chrome → Styled input  
- Some browsers → Ignore styling  

👉 **Lesson:**
- Standards exist, but **implementation varies**

---

## 🛠️ Handling Inconsistencies

### Example: Feature Detection

    if ('geolocation' in navigator) {
      console.log("Geolocation supported");
    } else {
      console.log("Not supported");
    }

👉 **Engineering Insight:**
- Don’t assume support  
- Always check capabilities

---

## 🔄 Progressive Enhancement Example

### Basic Version (Works Everywhere)

    <button>Submit</button>

### Enhanced Version

    document.querySelector("button").addEventListener("click", () => {
      alert("Form submitted!");
    });

👉 **Engineering Insight:**
- Core functionality first  
- Enhancements added for capable environments  

---

## 🔐 Standards and Security Example

### Non-secure Request

    http://example.com/login

### Secure Standard

    https://example.com/login

👉 **Engineering Insight:**
- Standards enforce **secure communication**

---

## 🧠 Key Takeaways from Code

- Standards eliminate ambiguity  
- Not all browsers behave the same  
- Developers must design for **variability**  
- Writing code is easy; writing **robust code** is engineering  

---

## 📝 In-Class Activity

Analyze this:

    <b>Important</b>

👉 Questions:
- Is this semantic?  
- What is the better standard-compliant alternative?  

---

## 📌 Summary

- Web standards guide correct implementation  
- Code examples reveal real-world issues  
- Engineers must:
  - Choose standard approaches  
  - Handle inconsistencies  
  - Design for reliability  

---

## ❓ Quick Questions

1. What are web standards?  
2. Name two organizations responsible for web standards  
3. Why is cross-browser compatibility important?  
4. What is the difference between a standard and its implementation?  

---

## 🚀 Next Lecture

**Constraints of the Web Platform (Why the Web is Different from Traditional Systems)**

---
