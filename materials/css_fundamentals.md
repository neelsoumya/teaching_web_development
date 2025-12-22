# Cascading Style Sheets (CSS) Fundamentals

[Video by Dr. Chuck on CSS Basics](https://youtu.be/b99aHsUi7Zk?si=O4qkBOn6LzZgFGwz): A beginner-friendly video explaining the fundamentals of CSS.

## Lecture Outline

### Part 1: Introduction to CSS (30 minutes)

#### 1.1 What is CSS?
- **CSS**: Cascading Style Sheets
- Controls presentation and layout
- Separates content from design
- Current version: CSS3

#### 1.2 How CSS Works
- Cascading: Multiple style sources (browser, author, user)
- Inheritance: Child elements inherit parent styles
- Specificity: Which rule wins when conflicts occur

#### 1.3 Three Ways to Add CSS

**Inline CSS (avoid except for dynamic styles):**
```html
<p style="color: blue; font-size: 16px;">Text</p>
```

**Internal CSS:**
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
```

**External CSS (best practice):**
```html
<head>
    <link rel="stylesheet" href="css/style.css">
</head>
```

```css
/* style.css */
p {
    color: blue;
    font-size: 16px;
}
```

### Part 2: CSS Selectors (45 minutes)

#### 2.1 Basic Selectors

**Element Selector:**
```css
p {
    color: black;
}

h1 {
    font-size: 32px;
}
```

**Class Selector:**
```css
.highlight {
    background-color: yellow;
}

.btn {
    padding: 10px 20px;
    border-radius: 5px;
}
```

```html
<p class="highlight">Highlighted text</p>
<button class="btn">Click Me</button>
```

**ID Selector:**
```css
#header {
    background-color: navy;
}

#main-content {
    padding: 20px;
}
```

```html
<div id="header">Header Content</div>
<div id="main-content">Main Content</div>
```

**Universal Selector:**
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

#### 2.2 Combinators

**Descendant Selector (space):**
```css
/* All p elements inside div */
div p {
    color: blue;
}
```

**Child Selector (>):**
```css
/* Only direct children */
div > p {
    font-weight: bold;
}
```

**Adjacent Sibling (+):**
```css
/* p immediately after h2 */
h2 + p {
    margin-top: 0;
}
```

**General Sibling (~):**
```css
/* All p elements after h2 */
h2 ~ p {
    color: gray;
}
```

#### 2.3 Attribute Selectors

```css
/* Has attribute */
input[required] {
    border: 2px solid red;
}

/* Exact value */
input[type="email"] {
    background-color: lightyellow;
}

/* Contains value */
a[href*="example"] {
    color: green;
}

/* Starts with */
a[href^="https"] {
    padding-left: 20px;
}

/* Ends with */
a[href$=".pdf"] {
    color: red;
}
```

#### 2.4 Pseudo-classes

```css
/* Link states */
a:link { color: blue; }
a:visited { color: purple; }
a:hover { color: red; }
a:active { color: orange; }

/* Form states */
input:focus {
    outline: 2px solid blue;
}

input:disabled {
    background-color: #eee;
}

input:checked + label {
    font-weight: bold;
}

/* Structural */
li:first-child {
    font-weight: bold;
}

li:last-child {
    border-bottom: none;
}

li:nth-child(odd) {
    background-color: #f0f0f0;
}

li:nth-child(3n) {
    color: red;
}

p:not(.special) {
    color: gray;
}
```

#### 2.5 Pseudo-elements

```css
/* First line/letter */
p::first-line {
    font-weight: bold;
}

p::first-letter {
    font-size: 2em;
    float: left;
}

/* Before/After */
.quote::before {
    content: """;
    font-size: 2em;
}

.quote::after {
    content: """;
    font-size: 2em;
}

/* Selection */
::selection {
    background-color: yellow;
    color: black;
}
```

### Part 3: CSS Properties (60 minutes)

#### 3.1 Color and Background

**Color Values:**
```css
/* Named colors */
color: red;

/* Hexadecimal */
color: #FF0000;
color: #F00; /* shorthand */

/* RGB */
color: rgb(255, 0, 0);

/* RGBA (with transparency) */
color: rgba(255, 0, 0, 0.5);

/* HSL */
color: hsl(0, 100%, 50%);

/* HSLA */
color: hsla(0, 100%, 50%, 0.5);
```

**Background Properties:**
```css
.element {
    background-color: #f0f0f0;
    background-image: url('bg.jpg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    background-attachment: fixed;
    
    /* Shorthand */
    background: #f0f0f0 url('bg.jpg') no-repeat center/cover;
}

/* Multiple backgrounds */
.hero {
    background: 
        url('overlay.png'),
        url('photo.jpg');
    background-size: cover, cover;
}

/* Gradients */
.gradient {
    background: linear-gradient(to right, red, blue);
    background: linear-gradient(45deg, red, yellow, blue);
    background: radial-gradient(circle, red, blue);
}
```

#### 3.2 Text Styling

**Font Properties:**
```css
.text {
    /* Font family */
    font-family: Arial, Helvetica, sans-serif;
    font-family: 'Times New Roman', serif;
    font-family: 'Courier New', monospace;
    
    /* Font size */
    font-size: 16px;
    font-size: 1.2em;  /* relative to parent */
    font-size: 1.2rem; /* relative to root */
    
    /* Font weight */
    font-weight: normal;
    font-weight: bold;
    font-weight: 700;
    
    /* Font style */
    font-style: italic;
    font-style: oblique;
    
    /* Shorthand */
    font: italic bold 16px/1.5 Arial, sans-serif;
}
```

**Text Properties:**
```css
.paragraph {
    /* Alignment */
    text-align: left;
    text-align: center;
    text-align: right;
    text-align: justify;
    
    /* Decoration */
    text-decoration: underline;
    text-decoration: line-through;
    text-decoration: none;
    
    /* Transform */
    text-transform: uppercase;
    text-transform: lowercase;
    text-transform: capitalize;
    
    /* Spacing */
    letter-spacing: 2px;
    word-spacing: 5px;
    line-height: 1.6;
    
    /* Indent */
    text-indent: 50px;
    
    /* Shadow */
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}
```

**Web Fonts:**
```html
<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
```

```css
body {
    font-family: 'Roboto', sans-serif;
}
```

#### 3.3 Units of Measurement

**Absolute Units:**
```css
/* Pixels (most common) */
font-size: 16px;

/* Points (print) */
font-size: 12pt;

/* Inches, cm, mm (rarely used) */
width: 2in;
```

**Relative Units:**
```css
/* em - relative to parent font-size */
font-size: 1.5em;  /* 1.5 times parent */

/* rem - relative to root (html) font-size */
font-size: 1.5rem;

/* Percentage */
width: 50%;
font-size: 120%;

/* Viewport units */
width: 50vw;  /* 50% of viewport width */
height: 100vh; /* 100% of viewport height */
font-size: 5vmin; /* 5% of smaller dimension */
```

### Part 4: The Box Model (45 minutes)

#### 4.1 Understanding the Box Model

Every element is a rectangular box with:
1. **Content**: The actual content
2. **Padding**: Space inside the border
3. **Border**: Line around padding
4. **Margin**: Space outside the border

```css
.box {
    /* Content area */
    width: 300px;
    height: 200px;
    
    /* Padding (inside) */
    padding: 20px;
    padding: 10px 20px; /* vertical horizontal */
    padding: 10px 20px 30px 40px; /* top right bottom left */
    
    /* Border */
    border: 2px solid black;
    border-width: 2px;
    border-style: solid;
    border-color: black;
    border-radius: 10px;
    
    /* Margin (outside) */
    margin: 20px;
    margin: 10px auto; /* center horizontally */
    
    /* Box-sizing */
    box-sizing: border-box; /* includes padding and border in width */
}
```

#### 4.2 Box Sizing

**Content-box (default):**
```css
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Actual width = 300 + 40 + 10 = 350px */
}
```

**Border-box (recommended):**
```css
* {
    box-sizing: border-box;
}

.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Actual width = 300px (includes padding and border) */
}
```

#### 4.3 Display Property

```css
/* Block elements (full width) */
div {
    display: block;
}

/* Inline elements (only content width) */
span {
    display: inline;
}

/* Inline-block (inline but can have width/height) */
.button {
    display: inline-block;
    width: 200px;
    padding: 10px;
}

/* Hide element */
.hidden {
    display: none;
}

/* Flex and Grid (next week) */
.container {
    display: flex;
    display: grid;
}
```

#### 4.4 Visibility

```css
/* Hide but keep space */
.invisible {
    visibility: hidden;
}

/* Hide completely */
.gone {
    display: none;
}

/* Transparent */
.see-through {
    opacity: 0.5;
}
```

### Part 5: Positioning (30 minutes)

#### 5.1 Position Property

**Static (default):**
```css
.element {
    position: static; /* Normal flow */
}
```

**Relative:**
```css
.element {
    position: relative;
    top: 20px;    /* Move down from normal position */
    left: 10px;   /* Move right from normal position */
}
```

**Absolute:**
```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    top: 0;
    right: 0; /* Position relative to parent */
}
```

**Fixed:**
```css
.navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000; /* Stack order */
}
```

**Sticky:**
```css
.sidebar {
    position: sticky;
    top: 20px; /* Sticks when scrolling */
}
```

#### 5.2 Z-index

```css
.layer1 {
    position: relative;
    z-index: 1;
}

.layer2 {
    position: relative;
    z-index: 2; /* Appears on top */
}

.modal {
    position: fixed;
    z-index: 9999; /* Very top */
}
```

#### 5.3 Float (legacy layout)

```css
.sidebar {
    float: left;
    width: 30%;
}

.main {
    float: right;
    width: 68%;
}

.clearfix::after {
    content: "";
    display: table;
    clear: both;
}
```

## Key Takeaways

1. CSS selectors target HTML elements for styling
2. Specificity determines which styles apply
3. Box model controls spacing and layout
4. Position property controls element placement
5. Use relative units for responsive design

## Practice Exercises

1. Create a styled button with hover effects
2. Build a card component with image and text
3. Style a navigation menu
4. Create a hero section with background image

## Required Reading
- MDN CSS Basics
- CSS Specificity Calculator
- Box Model interactive demo

## Next Week Preview
- Flexbox layout
- CSS Grid
- Responsive design
- Media queries
