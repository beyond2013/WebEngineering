# 🛠️ Instructor’s Note on AI & Ethics
> **Declaration:** Portions of this material were generated with the assistance of AI (ChatGPT, OpenAI, Google Gemini) and curated by the instructor.  
> Students are advised to consult standard references to validate and deepen their understanding.
---

# Week 6: CSS Layouts  
## Flexbox, Grid, Responsive Design & Media Queries

---

# Learning Outcomes

By the end of this lecture, students will be able to:

- Understand modern CSS layout techniques
- Use Flexbox to align and distribute elements
- Create structured layouts using CSS Grid
- Understand the concept of responsive web design
- Use media queries to adapt layouts to different screen sizes
- Convert a fixed/static webpage into a responsive webpage

---

# Recap of Previous Lecture (Week 5)

Previously, students learned:

- CSS syntax and selectors
- Inline, internal, and external CSS
- Colors, fonts, borders, and backgrounds
- CSS box model
- Margins and padding
- Basic styling of webpages 

---
# Introduction to CSS Layouts

Earlier websites relied heavily on:

- HTML tables
- Floats
- Manual spacing
- CSS positioning

These methods were difficult to maintain and not responsive.

To better understand modern layouts, it is important to briefly understand how traditional positioning worked in CSS.

---

# Traditional CSS Positioning

The `position` property controls how an element is placed on a webpage.

Common values include:

| Value | Meaning |
|---|---|
| static | Default positioning |
| relative | Moves relative to original position |
| absolute | Positioned relative to nearest positioned parent |
| fixed | Stays fixed on screen |
| sticky | Switches between relative and fixed |

---

# Static Positioning

Default behavior of HTML elements.

```css
position: static;
```

Elements appear in normal document flow.

---

# Relative Positioning

Moves an element relative to its original position.

```css
.box{
    position: relative;
    left: 20px;
    top: 10px;
}
```

---

# Absolute Positioning

Removes the element from normal document flow.

```css
.box{
    position: absolute;
    top: 50px;
    right: 20px;
}
```

Usually used inside a positioned parent container.

---

# Fixed Positioning

The element stays fixed even when the page scrolls.

```css
header{
    position: fixed;
    top: 0;
}
```

Commonly used for navigation bars.

---

# Sticky Positioning

Acts like relative positioning until scrolling reaches a threshold.

```css
.sidebar{
    position: sticky;
    top: 0;
}
```

Commonly used in side menus and table headers.

---

# Limitations of Traditional Positioning

Although positioning is still useful, building complete layouts using only positioning becomes difficult because:

- Elements may overlap
- Responsive design becomes harder
- Vertical alignment is difficult
- Layouts require excessive manual adjustments
- Maintaining large websites becomes complicated

As web applications became more complex and mobile devices became common, developers needed better layout systems.

Modern CSS therefore introduced:

1. **Flexbox** → One-dimensional layouts  
2. **Grid** → Two-dimensional layouts  
3. **Responsive Design** → Layouts adapting to screen size  

These modern systems make layouts cleaner, more flexible, and easier to maintain.

---

# Why Layout Systems Matter

A good layout system helps us:

- Align content properly
- Build responsive websites
- Reduce unnecessary code
- Improve user experience
- Support mobile devices

Examples:

- Navigation bars
- Dashboards
- Product galleries
- Responsive forms
- News portals

---

# Part 1 — Flexbox

# What is Flexbox?

Flexbox (Flexible Box Layout) is a CSS layout model used for arranging items in:

- A row
- A column

It is ideal for:

- Navigation bars
- Menus
- Cards
- Centering elements
- Responsive alignment

---

# Flexbox Terminology

## Parent Element

The parent becomes a **flex container**.

```css
.container{
    display: flex;
}
```

## Child Elements

The children become **flex items**.

---

# Basic Flexbox Example

```html
<!DOCTYPE html>
<html>
<head>
<style>

.container{
    display:flex;
    border:2px solid black;
}

.box{
    width:100px;
    height:100px;
    margin:10px;
    background-color:skyblue;
}

</style>
</head>

<body>

<div class="container">

    <div class="box">1</div>
    <div class="box">2</div>
    <div class="box">3</div>

</div>

</body>
</html>
```

---

# Default Flex Direction

By default:

```css
flex-direction: row;
```

Items appear horizontally.

---

# Column Layout

```css
.container{
    display:flex;
    flex-direction:column;
}
```

Items appear vertically.

---

# Main Axis vs Cross Axis

In Flexbox:

- Main axis → direction of flex items
- Cross axis → perpendicular direction

Example:

| flex-direction | Main Axis |
|---|---|
| row | Horizontal |
| column | Vertical |

---

# Justify Content

Controls alignment on the **main axis**.

```css
justify-content:center;
```

Other values:

```css
justify-content:flex-start;
justify-content:flex-end;
justify-content:space-between;
justify-content:space-around;
justify-content:space-evenly;
```

---

# Example: Space Between

```css
.container{
    display:flex;
    justify-content:space-between;
}
```

Items spread evenly.

---

# Align Items

Controls alignment on the **cross axis**.

```css
align-items:center;
```

Other values:

```css
align-items:flex-start;
align-items:flex-end;
align-items:stretch;
```

---

# Centering Using Flexbox

```css
.container{
    display:flex;
    justify-content:center;
    align-items:center;
    height:300px;
}
```

Very commonly used in modern UI design.

---

# Flex Wrap

Without wrapping, items shrink.

```css
flex-wrap:wrap;
```

Allows items to move to next line.

---

# Flexbox Mini Project

## Responsive Navigation Bar

```html
<!DOCTYPE html>
<html>
<head>
<style>

nav{
    display:flex;
    justify-content:space-between;
    background-color:#333;
    padding:15px;
}

.logo{
    color:white;
    font-size:24px;
}

.menu{
    display:flex;
    gap:20px;
}

.menu a{
    color:white;
    text-decoration:none;
}

</style>
</head>

<body>

<nav>

<div class="logo">MySite</div>

<div class="menu">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
</div>

</nav>

</body>
</html>
```

---

# Part 2 — CSS Grid

# What is CSS Grid?

CSS Grid is a **two-dimensional layout system**.

It controls:

- Rows
- Columns

Best for:

- Full webpage layouts
- Dashboards
- Gallery layouts
- Complex responsive designs

---

# Creating a Grid Container

```css
.container{
    display:grid;
}
```

---

# Defining Columns

```css
.container{
    display:grid;
    grid-template-columns:200px 200px 200px;
}
```

Creates 3 columns.

---

# Using Fraction Units

```css
grid-template-columns:1fr 1fr 1fr;
```

`fr` means fraction of available space.

---

# Grid Gap

```css
gap:20px;
```

Adds spacing between rows and columns.

---

# Basic Grid Example

```html
<!DOCTYPE html>
<html>
<head>
<style>

.container{
    display:grid;
    grid-template-columns:1fr 1fr 1fr;
    gap:20px;
}

.box{
    background-color:lightgreen;
    padding:40px;
    text-align:center;
}

</style>
</head>

<body>

<div class="container">

    <div class="box">1</div>
    <div class="box">2</div>
    <div class="box">3</div>
    <div class="box">4</div>
    <div class="box">5</div>
    <div class="box">6</div>

</div>

</body>
</html>
```

---

# Grid Row and Column Span

## Column Span

```css
grid-column:1 / 3;
```

The item spans two columns.

---

# Row Span

```css
grid-row:1 / 3;
```

The item spans two rows.

---

# Example Layout

```css
.container{
    display:grid;
    grid-template-columns:1fr 1fr 1fr;
    gap:10px;
}

.header{
    grid-column:1 / 4;
}
```

Header spans all columns.

---

# Flexbox vs Grid

| Feature | Flexbox | Grid |
|---|---|---|
| Dimension | One-dimensional | Two-dimensional |
| Best For | Small components | Full layouts |
| Direction | Row OR Column | Rows AND Columns |
| Complexity | Simpler | More powerful |

---

# Part 3 — Responsive Design

# What is Responsive Design?

Responsive design means:

> A website adjusts itself according to screen size.

The same website should work on:

- Mobile phones
- Tablets
- Laptops
- Desktop computers

---

# Why Responsive Design Matters

Today most users browse from mobile devices.

A responsive website:

- Improves usability
- Improves readability
- Reduces zooming and scrolling
- Provides better user experience

---

# Common Screen Sizes

| Device | Width |
|---|---|
| Mobile | < 768px |
| Tablet | 768px – 1024px |
| Desktop | > 1024px |

---

# Responsive Units

Instead of fixed pixels, responsive layouts use:

| Unit | Meaning |
|---|---|
| % | Percentage |
| vw | Viewport width |
| vh | Viewport height |
| rem | Relative font size |
| fr | Fractional grid unit |

---

# Example: Responsive Width

```css
.container{
    width:80%;
}
```

Better than:

```css
width:800px;
```

---

# Images in Responsive Design

```css
img{
    max-width:100%;
    height:auto;
}
```

Images scale automatically.

---

# Part 4 — Media Queries

# What are Media Queries?

Media queries apply CSS rules based on screen size.

---

# Basic Syntax

```css
@media screen and (max-width:768px){

}
```

---

# Example: Mobile Layout

```css
.container{
    display:flex;
    flex-direction:row;
}

@media screen and (max-width:768px){

.container{
    flex-direction:column;
}

}
```

Desktop:
- Horizontal layout

Mobile:
- Vertical layout

---

# Responsive Navigation Example

```html
<!DOCTYPE html>
<html>
<head>

<style>

nav{
    display:flex;
    justify-content:space-between;
    background-color:black;
    padding:15px;
}

.menu{
    display:flex;
    gap:20px;
}

a{
    color:white;
    text-decoration:none;
}

@media screen and (max-width:600px){

    nav{
        flex-direction:column;
        align-items:center;
    }

    .menu{
        flex-direction:column;
        margin-top:10px;
    }
}

</style>
</head>

<body>

<nav>

<h2 style="color:white;">LOGO</h2>

<div class="menu">
    <a href="#">Home</a>
    <a href="#">Services</a>
    <a href="#">Contact</a>
</div>

</nav>

</body>
</html>
```

---

# Best Practices for Responsive Design

- Start with simple layouts
- Avoid fixed widths
- Use Flexbox and Grid
- Test on multiple screen sizes
- Keep navigation mobile-friendly
- Use scalable images

---

# Common Mistakes

| Mistake | Problem |
|---|---|
| Fixed widths | Breaks on mobile |
| Too much text | Difficult to read |
| Tiny buttons | Hard to click |
| Large images | Slow loading |
| No media queries | Poor responsiveness |

---

# Real-World Applications

Flexbox and Grid are used in:

- Facebook
- YouTube
- Amazon
- Dashboards
- Admin panels
- Portfolio websites
- E-commerce websites

---

# In-Class Activity

## Activity: Build a Responsive Card Layout

Students create:

- 3 cards in desktop view
- 1-column layout on mobile

Requirements:

- Use Flexbox or Grid
- Add image and text
- Add media query

---

# Lab Task

# Lab: Convert Static Page into Responsive Layout

## Objective

Convert a fixed/static webpage into a responsive webpage using:

- Flexbox
- Grid
- Media queries

---

# Given Static Layout

Students are given:

- Header
- Sidebar
- Main content
- Footer

Initially designed only for desktop.

---

# Requirements

Students must:

1. Convert navigation into Flexbox
2. Use Grid for content section
3. Add responsive media query
4. Make layout mobile-friendly
5. Ensure images resize properly

---

# Suggested Breakpoints

```css
@media screen and (max-width:768px)
```

---

# Expected Mobile Behavior

Desktop:

```text
Sidebar | Content
```

Mobile:

```text
Sidebar
Content
```

---

# Suggested Lab Structure

```text
project/
│
├── index.html
├── style.css
└── images/
```

---

# Assessment Criteria

| Criteria | Marks |
|---|---|
| Proper Flexbox Usage | 5 |
| Proper Grid Usage | 5 |
| Media Queries | 5 |
| Mobile Responsiveness | 5 |
| Code Organization | 5 |

---

# Summary of Today’s Lecture

Today we learned:

- Flexbox basics
- Grid layouts
- Responsive web design
- Media queries
- Mobile-friendly layouts

---

# Preview of Next Lecture (Week 7)

Next week:

- CSS Transitions
- CSS Animations
- Transformations
- Hover Effects
- Simple UI Effects

---

# Practice Exercises

1. Create a responsive navbar using Flexbox  
2. Design a photo gallery using Grid  
3. Make a webpage responsive for mobile devices  
4. Create a two-column layout that becomes one-column on mobile  
5. Add media queries for tablets and mobiles  

---

# End of Lecture

**Thank You*