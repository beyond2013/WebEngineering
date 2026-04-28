# Week 4: Advanced HTML  
## Lecture 4 — Lists, Tables, Forms, Semantic HTML & Accessibility

---

## 1. Recap of Previous Lecture (Week 3)

In the previous lecture, we learned:

- Basic structure of an HTML document
- Headings, paragraphs, links, and images
- Importance of document structure using HTML tags

**Key idea:** HTML defines *structure and meaning*, not styling.

---

## 2. Lists in HTML

Lists help organize related items.

### Ordered List (sequence matters)

<pre>
&lt;ol&gt;
  &lt;li&gt;Register student&lt;/li&gt;
  &lt;li&gt;Assign roll number&lt;/li&gt;
  &lt;li&gt;Generate ID card&lt;/li&gt;
&lt;/ol&gt;
</pre>

---

### Unordered List (no order required)

<pre>
&lt;ul&gt;
  &lt;li&gt;HTML&lt;/li&gt;
  &lt;li&gt;CSS&lt;/li&gt;
  &lt;li&gt;JavaScript&lt;/li&gt;
&lt;/ul&gt;
</pre>

---

### Nested List

<pre>
&lt;ul&gt;
  &lt;li&gt;Programming
    &lt;ul&gt;
      &lt;li&gt;C++&lt;/li&gt;
      &lt;li&gt;Java&lt;/li&gt;
    &lt;/ul&gt;
  &lt;/li&gt;
&lt;/ul&gt;
</pre>

---

## 3. Tables in HTML

Tables are used for structured data.

<pre>
&lt;table border="1"&gt;
  &lt;tr&gt;
    &lt;th&gt;Roll No&lt;/th&gt;
    &lt;th&gt;Name&lt;/th&gt;
    &lt;th&gt;CGPA&lt;/th&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
    &lt;td&gt;101&lt;/td&gt;
    &lt;td&gt;Ayesha&lt;/td&gt;
    &lt;td&gt;3.5&lt;/td&gt;
  &lt;/tr&gt;
&lt;/table&gt;
</pre>

**Key elements:**
- table → container
- tr → row
- th → header cell
- td → data cell

---

## 4. Forms in HTML

Forms collect user input.

### Basic Form

<pre>
&lt;form&gt;
  Name: &lt;input type="text"&gt;
  Email: &lt;input type="email"&gt;
  Password: &lt;input type="password"&gt;

  &lt;input type="submit" value="Register"&gt;
&lt;/form&gt;
</pre>

---

### Radio Buttons

<pre>
Gender:
&lt;input type="radio" name="gender" value="male"&gt; Male
&lt;input type="radio" name="gender" value="female"&gt; Female
</pre>

---

### Dropdown List

<pre>
&lt;select&gt;
  &lt;option&gt;CS&lt;/option&gt;
  &lt;option&gt;IT&lt;/option&gt;
  &lt;option&gt;SE&lt;/option&gt;
&lt;/select&gt;
</pre>

---

## 5. Semantic HTML

Semantic tags describe meaning clearly.

### Why semantic HTML?

- Better readability
- Better SEO
- Better accessibility
- Professional coding practice

---

### Header

<pre>
&lt;header&gt;
  &lt;h1&gt;University Portal&lt;/h1&gt;
&lt;/header&gt;
</pre>

---

### Navigation

<pre>
&lt;nav&gt;
  &lt;a href="home.html"&gt;Home&lt;/a&gt;
  &lt;a href="about.html"&gt;About&lt;/a&gt;
&lt;/nav&gt;
</pre>

---

### Main Section

<pre>
&lt;main&gt;
  &lt;section&gt;
    &lt;h2&gt;Welcome&lt;/h2&gt;
    &lt;p&gt;Main content goes here&lt;/p&gt;
  &lt;/section&gt;
&lt;/main&gt;
</pre>

---

### Article

<pre>
&lt;article&gt;
  &lt;h2&gt;Latest News&lt;/h2&gt;
  &lt;p&gt;Semester schedule announced&lt;/p&gt;
&lt;/article&gt;
</pre>

---

### Footer

<pre>
&lt;footer&gt;
  &lt;p&gt;Contact: info@university.edu&lt;/p&gt;
&lt;/footer&gt;
</pre>

---

## 6. Accessibility Basics

Accessibility ensures websites work for everyone.

### Important Practices

#### ALT text for images
<pre>
&lt;img src="campus.jpg" alt="University campus building"&gt;
</pre>

---

#### Labels for form inputs
<pre>
&lt;label for="name"&gt;Name:&lt;/label&gt;
&lt;input id="name" type="text"&gt;
</pre>

---

#### Avoid vague links

Bad:
Click here

Good:
View admission details

---

## 7. Lab Task — Student Registration Form

### Objective:
Design a structured registration form.

### Requirements:
- Name
- Email
- Password
- Gender
- Department
- Courses
- Address

---

### Sample Solution

<pre>
&lt;form&gt;

  Full Name: &lt;input type="text"&gt;

  Email: &lt;input type="email"&gt;

  Password: &lt;input type="password"&gt;

  Gender:
  &lt;input type="radio" name="gender"&gt; Male
  &lt;input type="radio" name="gender"&gt; Female

  Department:
  &lt;select&gt;
    &lt;option&gt;CS&lt;/option&gt;
    &lt;option&gt;IT&lt;/option&gt;
    &lt;option&gt;SE&lt;/option&gt;
  &lt;/select&gt;

  Courses:
  &lt;input type="checkbox"&gt; Web Engineering
  &lt;input type="checkbox"&gt; DBMS

  Address:
  &lt;textarea&gt;&lt;/textarea&gt;

  &lt;input type="submit" value="Register"&gt;

&lt;/form&gt;
</pre>

---

## 8. Key Takeaways

- Lists organize content
- Tables structure data
- Forms collect input
- Semantic HTML adds meaning
- Accessibility improves usability for all users

---

## Next Lecture (Week 5)

CSS Basics:
- Selectors
- Colors
- Box Model
- Simple page styling
