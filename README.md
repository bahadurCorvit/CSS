# CSS Learning Roadmap

## Introduction to CSS
Cascading Style Sheets (CSS) is a stylesheet language used to control the presentation of web pages. It allows you to style HTML elements efficiently and consistently across multiple pages.

---

### 1. CSS Basics
#### Types of CSS:
- **Inline CSS**: Applied directly to an HTML element using the `style` attribute.
- **Internal CSS**: Defined within a `<style>` tag inside the `<head>` section of an HTML document.
- **External CSS**: Written in a separate `.css` file and linked to the HTML document using the `<link>` tag.

### 2. Selectors
CSS selectors define which elements should be styled. Common selectors include:
- **Element Selector**: Targets HTML elements (`p`, `h1`, `div`, etc.).
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Element Selector Example</title>
    <style>
        p {
            color: blue;
        }
        h1 {
            font-size: 2em;
        }
    </style>
</head>
<body>
    <h1>This is a Heading</h1>
    <p>This is a paragraph.</p>
</body>
</html>

```
- **Class Selector**: Targets elements with a specific class (`.classname`).
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Class Selector Example</title>
    <style>
        .highlight {
            background-color: yellow;
        }
        .bold-text {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <p class="highlight">This paragraph has a yellow background.</p>
    <p class="bold-text">This text is bold.</p>
    <p class="highlight bold-text">This text is both bold and highlighted.</p>
</body>
</html>

```

- **ID Selector**: Targets a unique element (`#idname`).
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ID Selector Example</title>
    <style>
        #unique {
            color: red;
            font-size: 1.5em;
        }
    </style>
</head>
<body>
    <p id="unique">This paragraph has a unique ID and is styled with the ID selector.</p>
</body>
</html>

```
- **Attribute Selector**: Selects elements based on attributes (`input[type='text']`).
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Attribute Selector Example</title>
    <style>
        input[type="text"] {
            border: 2px solid blue;
            padding: 5px;
        }
    </style>
</head>
<body>
    <input type="text" placeholder="Text input field">
    <input type="password" placeholder="Password input field">
</body>
</html>

```
- **Combinators**: Define relationships between elements (`div > p`, `ul li`, etc.).
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Combinators Example</title>
    <style>
        /* Direct child combinator: Selects <p> elements that are direct children of <div> */
        div > p {
            color: green;
        }

        /* Descendant combinator: Selects <li> elements that are inside <ul> */
        ul li {
            list-style-type: square;
        }
    </style>
</head>
<body>
    <div>
        <p>This paragraph is inside a div and will be green.</p>
        <p>This one too.</p>
    </div>

    <ul>
        <li>First list item with square bullets.</li>
        <li>Second list item with square bullets.</li>
    </ul>
</body>
</html>

```
### 3. Cascading & Specificity
- **Cascading**: Defines how CSS rules are applied and overridden.
- **Specificity**: Determines which CSS rule takes precedence when multiple rules apply to an element.
  - Inline styles have the highest specificity.
  - ID selectors are stronger than class and element selectors.
  - More specific rules override less specific rules.

### 4. Box Model
The box model describes how an element’s dimensions are calculated:
- **Margin**: Space outside the border.
- **Border**: A line surrounding the padding and content.
- **Padding**: Space between the content and the border.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Margin Example</title>
    <style>
        div {
            border: 2px solid black;
            padding: 20px;
            margin: 30px; /* Adds space outside the border */
        }
    </style>
</head>
<body>
    <div>
        This is a div with a margin of 30px outside the border.
    </div>
</body>
</html>

```
- **Content**: The actual content inside the element.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Content Example</title>
    <style>
        div {
            width: 200px;
            border: 2px solid black;
            padding: 20px;
            margin: 20px;
        }
    </style>
</head>
<body>
    <div>
        This is the actual content inside the div element.
    </div>
</body>
</html>

```
### 5. CSS Units
Different units define element sizes:
- **px (Pixels)**: Fixed unit, commonly used for precise sizing.
- **em**: Relative to the font-size of the parent element.
- **rem**: Relative to the font-size of the root element (`html`).
- **% (Percentage)**: Relative to the parent element’s size.
- **vw (Viewport Width)**: Percentage of the viewport width.
- **vh (Viewport Height)**: Percentage of the viewport height.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Units Example</title>
    <style>
        .pixel {
            width: 200px; /* Fixed width */
            background-color: lightblue;
        }

        .em {
            font-size: 2em; /* 2 times the parent font size */
        }

        .rem {
            font-size: 2rem; /* 2 times the root (html) font size */
        }

        .percent {
            width: 50%; /* 50% of the parent element */
            background-color: lightgreen;
        }

        .vw {
            width: 50vw; /* 50% of the viewport width */
            background-color: lightcoral;
        }

        .vh {
            height: 30vh; /* 30% of the viewport height */
            background-color: lightgoldenrodyellow;
        }
    </style>
</head>
<body>
    <div class="pixel">This div is 200px wide.</div>
    <p class="em">This text is 2em (relative to the parent font-size).</p>
    <p class="rem">This text is 2rem (relative to the root font-size).</p>
    <div class="percent">This div is 50% of the parent element.</div>
    <div class="vw">This div is 50vw (50% of the viewport width).</div>
    <div class="vh">This div is 30vh (30% of the viewport height).</div>
</body>
</html>

```
---
## Text & Colors

### 6. Typography  
- **font-family**: Defines the typeface of text.  
- **font-size**: Specifies the size of the text.  
- **line-height**: Controls the spacing between lines of text.  
- **letter-spacing**: Adjusts the space between characters.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Font Styling Example</title>
    <style>
        .text-style {
            font-family: Arial, sans-serif; /* Defines the font */
            font-size: 20px; /* Sets the text size */
            line-height: 1.5; /* Increases line spacing */
            letter-spacing: 2px; /* Adds space between characters */
        }
    </style>
</head>
<body>
    <p class="text-style">
        This is a styled paragraph with Arial font, 20px font size, 1.5 line height, and 2px letter spacing.
    </p>
</body>
</html>

```

### 7.  Color & Backgrounds  
- **rgb, rgba**: Defines colors using red, green, blue (with optional alpha for transparency).  
- **hsl**: Defines colors using hue, saturation, and lightness.  
- **hex**: Specifies colors using hexadecimal values.  
- **background-image**: Sets an image as the background of an element.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Color and Background Example</title>
    <style>
        .rgb {
            background-color: rgb(255, 0, 0); /* Red */
            color: white;
            padding: 10px;
        }

        .rgba {
            background-color: rgba(0, 0, 255, 0.5); /* Semi-transparent blue */
            color: white;
            padding: 10px;
        }

        .hsl {
            background-color: hsl(120, 100%, 50%); /* Bright green */
            color: white;
            padding: 10px;
        }

        .hex {
            background-color: #ffcc00; /* Yellow */
            color: black;
            padding: 10px;
        }

        .bg-image {
            background-image: url('https://via.placeholder.com/300'); /* Background image */
            background-size: cover;
            color: white;
            padding: 50px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="rgb">This div has an RGB background.</div>
    <div class="rgba">This div has an RGBA background (with transparency).</div>
    <div class="hsl">This div has an HSL background.</div>
    <div class="hex">This div has a HEX background.</div>
    <div class="bg-image">This div has a background image.</div>
</body>
</html>

```

### 8. Lists & Tables  
- **list-style**: Controls the appearance of list markers.  
- **border-collapse**: Specifies whether table borders should collapse into a single border.  
- **border-spacing**: Defines the space between table borders.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>List & Table Styling Example</title>
    <style>
        /* List Styling */
        .custom-list {
            list-style: square; /* Changes bullet points to squares */
        }

        /* Table Styling */
        table {
            width: 50%;
            border: 2px solid black;
            border-collapse: collapse; /* Merges table borders into one */
            margin-top: 20px;
        }

        td, th {
            border: 2px solid black;
            padding: 10px;
            text-align: center;
        }

        .spacing-table {
            border-collapse: separate; /* Keeps borders separate */
            border-spacing: 10px; /* Adds space between borders */
        }
    </style>
</head>
<body>

    <!-- List Example -->
    <ul class="custom-list">
        <li>Item One</li>
        <li>Item Two</li>
        <li>Item Three</li>
    </ul>

    <!-- Table Example (Collapsed Borders) -->
    <table>
        <tr>
            <th>Name</th>
            <th>Age</th>
        </tr>
        <tr>
            <td>John</td>
            <td>25</td>
        </tr>
        <tr>
            <td>Jane</td>
            <td>22</td>
        </tr>
    </table>

    <!-- Table Example (Separated Borders) -->
    <table class="spacing-table">
        <tr>
            <th>Country</th>
            <th>Capital</th>
        </tr>
        <tr>
            <td>USA</td>
            <td>Washington D.C.</td>
        </tr>
        <tr>
            <td>UK</td>
            <td>London</td>
        </tr>
    </table>

</body>
</html>

```

### 9. White Space & Hyphenation  
- **white-space**: Controls how white space is handled in elements.  
- **hyphens**: Manages word hyphenation behavior.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>White-space & Hyphens Example</title>
    <style>
        .nowrap {
            white-space: nowrap; /* Prevents text from wrapping */
            width: 200px;
            border: 1px solid black;
            padding: 5px;
            overflow: hidden;
        }

        .pre {
            white-space: pre; /* Preserves spaces and line breaks */
            border: 1px solid black;
            padding: 5px;
        }

        .hyphen-auto {
            width: 200px;
            border: 1px solid black;
            padding: 5px;
            word-wrap: break-word;
            hyphens: auto; /* Automatically hyphenates long words */
        }
    </style>
</head>
<body>

    <div class="nowrap">
        This is a long sentence that will not wrap to the next line.
    </div>

    <div class="pre">
        This       text preserves spaces
        and line breaks exactly as written.
    </div>

    <div class="hyphen-auto">
        This-is-an-example-of-a-very-long-word-that-might-need-hyphenation.
    </div>

</body>
</html>

```
---

## Layout Fundamentals  

### 10.  Display Property  
- **block**: Elements take up the full width available.  
- **inline**: Elements only take up as much width as necessary.  
- **inline-block**: Like inline but allows setting width and height.  
- **none**: Hides the element completely.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Display Property Example</title>
    <style>
        .block {
            display: block;
            width: 100%;
            background-color: lightblue;
            padding: 10px;
            margin-bottom: 10px;
        }

        .inline {
            display: inline;
            background-color: lightcoral;
            padding: 5px;
        }

        .inline-block {
            display: inline-block;
            width: 150px;
            background-color: lightgreen;
            padding: 10px;
            margin: 5px;
            text-align: center;
        }

        .hidden {
            display: none; /* Completely hides the element */
        }
    </style>
</head>
<body>

    <div class="block">This is a block element.</div>

    <span class="inline">This is an inline element.</span>
    <span class="inline">Another inline element.</span>

    <div class="inline-block">Inline-Block 1</div>
    <div class="inline-block">Inline-Block 2</div>

    <p class="hidden">This paragraph is hidden using `display: none;`</p>

</body>
</html>

```

### 11. Positioning  
- **static**: Default positioning (follows normal document flow).  
- **relative**: Positioned relative to its normal position.  
- **absolute**: Positioned relative to the nearest positioned ancestor.  
- **fixed**: Stays fixed relative to the viewport.  
- **sticky**: Toggles between relative and fixed based on scroll position.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Positioning Example</title>
    <style>
        .container {
            position: relative; /* Acts as the reference for absolute positioning */
            width: 300px;
            height: 200px;
            border: 2px solid black;
            margin-bottom: 20px;
        }

        .static {
            position: static; /* Default positioning */
            background-color: lightblue;
            padding: 10px;
        }

        .relative {
            position: relative;
            top: 20px;
            left: 20px;
            background-color: lightcoral;
            padding: 10px;
        }

        .absolute {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: lightgreen;
            padding: 10px;
        }

        .fixed {
            position: fixed;
            bottom: 10px;
            right: 10px;
            background-color: gold;
            padding: 10px;
        }

        .sticky {
            position: sticky;
            top: 0;
            background-color: orange;
            padding: 10px;
        }
    </style>
</head>
<body>

    <div class="static">This is static (default) positioning.</div>

    <div class="relative">This is relative positioning.</div>

    <div class="container">
        <div class="absolute">This is absolute positioning (inside container).</div>
    </div>

    <div class="sticky">This is sticky positioning (sticks when scrolling).</div>

    <div style="height: 1000px;">Scroll down to see the fixed element.</div>

    <div class="fixed">This is fixed positioning (always visible).</div>

</body>
</html>

```

### 12. Flexbox Basics  
- **display: flex**: Enables flexbox layout.  
- **flex-direction**: Defines the main axis (`row`, `column`).  
- **justify-content**: Aligns items along the main axis.  
- **align-items**: Aligns items along the cross axis.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox Example</title>
    <style>
        .container {
            display: flex; /* Enables flexbox */
            flex-direction: row; /* Main axis is horizontal */
            justify-content: center; /* Centers items horizontally */
            align-items: center; /* Centers items vertically */
            height: 200px;
            border: 2px solid black;
            background-color: lightgray;
        }

        .item {
            width: 50px;
            height: 50px;
            background-color: lightblue;
            margin: 5px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>

</body>
</html>

```

### 13. CSS Grid Basics  
- **grid-template-columns**: Defines the number and size of columns.  
- **grid-template-rows**: Defines the number and size of rows.  
- **gap**: Sets spacing between grid items.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Grid Example</title>
    <style>
        .grid-container {
            display: grid;
            grid-template-columns: 100px 100px 100px; /* Three columns of equal width */
            grid-template-rows: 100px 100px; /* Two rows of equal height */
            gap: 10px; /* Spacing between grid items */
            background-color: lightgray;
            padding: 10px;
        }

        .grid-item {
            background-color: lightblue;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            border: 2px solid black;
        }
    </style>
</head>
<body>

    <div class="grid-container">
        <div class="grid-item">1</div>
        <div class="grid-item">2</div>
        <div class="grid-item">3</div>
        <div class="grid-item">4</div>
        <div class="grid-item">5</div>
        <div class="grid-item">6</div>
    </div>

</body>
</html>

```

### 14. Float & Clear (Legacy)  
- **float**: Allows elements to be positioned to the left or right.  
- **clear**: Prevents elements from wrapping around floated elements.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Float and Clear Example</title>
    <style>
        .container {
            width: 300px;
            border: 2px solid black;
            padding: 10px;
        }

        .box {
            width: 100px;
            height: 100px;
            background-color: lightblue;
            text-align: center;
            line-height: 100px;
            font-weight: bold;
            margin: 5px;
        }

        .left {
            float: left;
        }

        .right {
            float: right;
        }

        .clear {
            clear: both; /* Ensures the next element starts below the floated elements */
            background-color: lightgray;
            padding: 10px;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="box left">Left</div>
        <div class="box right">Right</div>
        <div class="clear">This is below floated elements.</div>
    </div>

</body>
</html>

```
---
## Responsive Design & Media Queries  

### 15. Media Queries  
- **@media**: Applies styles based on different screen sizes.  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Media Query Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: lightgray;
            text-align: center;
        }

        .box {
            width: 100%;
            height: 200px;
            background-color: lightblue;
            margin: 20px 0;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 20px;
        }

        /* For screens wider than 600px */
        @media (min-width: 600px) {
            .box {
                background-color: lightcoral;
                font-size: 30px;
            }
        }

        /* For screens wider than 1000px */
        @media (min-width: 1000px) {
            .box {
                background-color: lightgreen;
                font-size: 40px;
            }
        }
    </style>
</head>
<body>

    <div class="box">Resize the window</div>

</body>
</html>

```  

### 16. Viewport Units  
- **vh (Viewport Height)**: Percentage of the viewport height.  
- **vw (Viewport Width)**: Percentage of the viewport width.  
- **vmin**: Smaller value of `vh` or `vw`.  
- **vmax**: Larger value of `vh` or `vw`.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Viewport Units Example</title>
    <style>
        body {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh; /* Makes the body fill the full viewport height */
            background-color: lightgray;
        }

        .box {
            width: 50vw; /* 50% of the viewport width */
            height: 50vh; /* 50% of the viewport height */
            background-color: lightblue;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2vmin; /* Font size based on the smaller of vh or vw */
            border: 2px solid black;
        }

        .box-large {
            width: 40vmax; /* 40% of the larger of vh or vw */
            height: 40vmax; /* 40% of the larger of vh or vw */
            background-color: lightcoral;
        }
    </style>
</head>
<body>

    <div class="box">
        <div class="box-large">
            Viewport Units
        </div>
    </div>

</body>
</html>
```

### 17. Aspect Ratio  
- **aspect-ratio**: Maintains element proportions.  

```html
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aspect Ratio Example</title>
    <style>
        body {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: lightgray;
        }

        .box {
            width: 50vw; /* 50% of the viewport width */
            aspect-ratio: 16 / 9; /* Maintains a 16:9 aspect ratio */
            background-color: lightblue;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 2rem;
        }
    </style>
</head>
<body>

    <div class="box">
        16:9 Aspect Ratio
    </div>

</body>
</html>

```  

### 18. Overflow & Scroll Behavior  
- **overflow**: Controls content overflow (`visible`, `hidden`, `scroll`, `auto`).  
- **scroll-behavior**: Defines how scrolling happens (`auto`, `smooth`). 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Overflow and Scroll Behavior Example</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
        }

        .container {
            width: 300px;
            height: 200px;
            margin: 50px auto;
            background-color: lightgray;
            overflow: scroll; /* Enables scrolling if content overflows */
            scroll-behavior: smooth; /* Smooth scrolling when the user scrolls */
            border: 2px solid black;
        }

        .content {
            height: 400px;
            padding: 10px;
            background-color: lightblue;
        }

        .hidden-content {
            width: 100%;
            height: 100px;
            overflow: hidden; /* Hides the overflowed content */
            background-color: lightcoral;
            text-align: center;
            line-height: 100px;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="content">
            Scroll down to see more content.
            <div class="hidden-content">Hidden Content</div>
        </div>
    </div>

</body>
</html>

```

### 19. Mobile-First & Adaptive Layouts  
- **Mobile-First Approach**: Designing for mobile first and scaling up for larger screens.  
- **Adaptive Layouts**: Using breakpoints to adjust designs for different devices.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mobile-First and Adaptive Layouts</title>
    <style>
        /* Mobile-First Styles */
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: lightgray;
            text-align: center;
            padding: 10px;
        }

        .container {
            background-color: lightblue;
            padding: 20px;
            border-radius: 8px;
        }

        .box {
            background-color: lightcoral;
            padding: 20px;
            border-radius: 8px;
            margin: 10px 0;
            font-size: 1.5rem;
        }

        /* For screens 600px and up (Tablets and Small Laptops) */
        @media (min-width: 600px) {
            .container {
                padding: 30px;
            }

            .box {
                font-size: 2rem;
            }
        }

        /* For screens 1000px and up (Desktops and Larger Screens) */
        @media (min-width: 1000px) {
            .container {
                width: 70%;
                margin: auto;
                padding: 40px;
            }

            .box {
                font-size: 2.5rem;
                margin: 20px 0;
            }
        }

    </style>
</head>
<body>

    <div class="container">
        <div class="box">Mobile-First Approach</div>
        <div class="box">Responsive Design Example</div>
    </div>

</body>
</html>

```
---

## Advanced Layout Techniques  

### 20. CSS Grid Advanced  
- **Named Areas**: Assign names to grid areas for better readability.  
  ```css
  .container {
    display: grid;
    grid-template-areas: 
      "header header"
      "sidebar content"
      "footer footer";
  }
  ```  
- **auto-fit & auto-fill**: Adjust column/row sizing dynamically.  
  ```css
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }
  ```  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Named Areas and Auto-fit/Auto-fill</title>
    <style>
        .container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); /* auto-fill: adjusts grid items dynamically */
            grid-template-rows: repeat(2, 200px); /* Two rows with fixed height */
            gap: 20px;
            grid-template-areas: 
                "header header"
                "main sidebar"
                "footer footer";
            padding: 20px;
        }

        .header {
            grid-area: header;
            background-color: lightblue;
            text-align: center;
            padding: 20px;
        }

        .main {
            grid-area: main;
            background-color: lightcoral;
            padding: 20px;
        }

        .sidebar {
            grid-area: sidebar;
            background-color: lightgreen;
            padding: 20px;
        }

        .footer {
            grid-area: footer;
            background-color: lightgoldenrodyellow;
            text-align: center;
            padding: 20px;
        }

    </style>
</head>
<body>

    <div class="container">
        <div class="header">Header (Full Width)</div>
        <div class="main">Main Content</div>
        <div class="sidebar">Sidebar</div>
        <div class="footer">Footer (Full Width)</div>
    </div>

</body>
</html>

```

### 21. Flexbox Advanced  
- **flex-grow**: Defines how much a flex item should grow.  
- **flex-shrink**: Determines how items shrink when necessary.  
- **align-self**: Aligns a single flex item differently from others. 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox Grow, Shrink, Align</title>
    <style>
        .container {
            display: flex;
            justify-content: space-between; /* Space between items */
            align-items: center; /* Vertically centers items */
            height: 300px;
            background-color: lightgray;
            padding: 20px;
        }

        .item {
            background-color: lightcoral;
            padding: 20px;
            text-align: center;
            font-size: 1.5rem;
            color: white;
        }

        .item-1 {
            flex-grow: 2; /* Will grow twice as much as other items */
        }

        .item-2 {
            flex-grow: 1; /* Default, will grow normally */
        }

        .item-3 {
            flex-shrink: 1; /* Will shrink when necessary */
        }

        .item-4 {
            flex-shrink: 0; /* Will not shrink, maintains its size */
        }

        .item-5 {
            align-self: flex-end; /* Aligns this item to the bottom of the container */
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="item item-1">Item 1 (Grow 2)</div>
        <div class="item item-2">Item 2 (Grow 1)</div>
        <div class="item item-3">Item 3 (Shrink 1)</div>
        <div class="item item-4">Item 4 (Shrink 0)</div>
        <div class="item item-5">Item 5 (Align Self)</div>
    </div>

</body>
</html>

```

### 22. Gap Property (Grid & Flexbox)  
- Adds spacing between elements in Grid and Flexbox.  
  ```css
  .container {
    display: flex;
    gap: 20px;
  }
  ``` 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid with Gap</title>
    <style>
        .grid-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-gap: 20px; /* Adds 20px gap between grid items */
            padding: 20px;
        }

        .grid-item {
            background-color: lightcoral;
            padding: 20px;
            text-align: center;
            font-size: 1.2rem;
            color: white;
        }
    </style>
</head>
<body>

    <div class="grid-container">
        <div class="grid-item">Item 1</div>
        <div class="grid-item">Item 2</div>
        <div class="grid-item">Item 3</div>
    </div>

</body>
</html>

```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox with Gap</title>
    <style>
        .flex-container {
            display: flex;
            gap: 20px; /* Adds 20px gap between flex items */
            padding: 20px;
        }

        .flex-item {
            background-color: lightcoral;
            padding: 20px;
            text-align: center;
            font-size: 1.2rem;
            color: white;
        }
    </style>
</head>
<body>

    <div class="flex-container">
        <div class="flex-item">Item 1</div>
        <div class="flex-item">Item 2</div>
        <div class="flex-item">Item 3</div>
    </div>

</body>
</html>

```

### 23. Z-index & Stacking Context  
- **z-index**: Controls element layering (higher values are on top).  
- **Stacking Context**: Defines how elements are layered based on parent-child relationships.  
  ```css
  .box {
    position: absolute;
    z-index: 10;
  }
  ```  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>z-index and Stacking Context</title>
    <style>
        .container {
            position: relative;
            width: 400px;
            height: 300px;
            background-color: lightgray;
            margin-top: 50px;
        }

        .box {
            position: absolute;
            width: 100px;
            height: 100px;
            text-align: center;
            color: white;
            font-size: 16px;
            padding-top: 30px;
        }

        .box-1 {
            background-color: lightcoral;
            left: 50px;
            top: 50px;
            z-index: 1; /* Will appear above box 2 */
        }

        .box-2 {
            background-color: lightblue;
            left: 100px;
            top: 100px;
            z-index: 0; /* Will appear below box 1 */
        }

        .box-3 {
            background-color: lightgreen;
            left: 150px;
            top: 150px;
            z-index: 2; /* Will appear on top of box 1 and box 2 */
        }

        .nested {
            position: relative;
            z-index: 3; /* Creates a new stacking context */
            width: 100px;
            height: 100px;
            background-color: lightyellow;
            top: 200px;
            left: 200px;
        }

        .nested-box {
            position: absolute;
            width: 60px;
            height: 60px;
            background-color: darkgray;
            z-index: 1; /* Works relative to the .nested context */
            top: 20px;
            left: 20px;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="box box-1">Box 1</div>
        <div class="box box-2">Box 2</div>
        <div class="box box-3">Box 3</div>

        <!-- Nested Stacking Context -->
        <div class="nested">
            <div class="nested-box">Nested Box</div>
        </div>
    </div>

</body>
</html>

```
---

## Styling Forms & UI Components  

### 24. Buttons & Forms  
- **input, button, textarea, select**: Core form elements.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Input Example</title>
</head>
<body>
    <form>
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" placeholder="Enter your name">
    </form>
</body>
</html>

```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Button Example</title>
</head>
<body>
    <button type="button" onclick="alert('Button clicked!')">Click Me</button>
</body>
</html>

```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Textarea Example</title>
</head>
<body>
    <form>
        <label for="message">Message:</label><br>
        <textarea id="message" name="message" rows="4" cols="50" placeholder="Type your message here"></textarea>
    </form>
</body>
</html>

```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Select Example</title>
</head>
<body>
    <form>
        <label for="car">Choose a car:</label>
        <select id="car" name="car">
            <option value="volvo">Volvo</option>
            <option value="saab">Saab</option>
            <option value="mercedes">Mercedes</option>
            <option value="audi">Audi</option>
        </select>
    </form>
</body>
</html>

```

### 25. Custom UI Elements  
- **Checkboxes & Radio Buttons**: Styled using `appearance` or pseudo-elements.  
- **Sliders**: Custom styles for `<input type="range">`.  
```html
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Checkbox Example</title>
    <style>
        /* Custom Style for Checkbox */
        input[type="checkbox"] {
            appearance: none;
            width: 20px;
            height: 20px;
            border: 2px solid #555;
            border-radius: 4px;
            background-color: white;
            position: relative;
            cursor: pointer;
        }

        /* When checked */
        input[type="checkbox"]:checked {
            background-color: #4CAF50;
            border-color: #4CAF50;
        }

        /* Custom Checkmark */
        input[type="checkbox"]:checked::after {
            content: "✔";
            position: absolute;
            top: 2px;
            left: 5px;
            color: white;
        }
    </style>
</head>
<body>
    <label>
        <input type="checkbox"> Accept Terms & Conditions
    </label>
</body>
</html>

```  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Radio Button Example</title>
    <style>
        /* Custom Style for Radio Button */
        input[type="radio"] {
            appearance: none;
            width: 20px;
            height: 20px;
            border: 2px solid #555;
            border-radius: 50%;
            background-color: white;
            position: relative;
            cursor: pointer;
        }

        /* When selected */
        input[type="radio"]:checked {
            background-color: #2196F3;
            border-color: #2196F3;
        }

        /* Custom Inner Circle */
        input[type="radio"]:checked::after {
            content: "";
            position: absolute;
            top: 4px;
            left: 4px;
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background-color: white;
        }
    </style>
</head>
<body>
    <label>
        <input type="radio" name="color" value="red"> Red
    </label>
    <label>
        <input type="radio" name="color" value="blue"> Blue
    </label>
</body>
</html>

```
#### Slider
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Slider Example</title>
    <style>
        /* Slider Container */
        input[type="range"] {
            width: 100%;
            height: 10px;
            background: #ddd;
            border-radius: 5px;
            outline: none;
            appearance: none;
        }

        /* Slider Thumb */
        input[type="range"]::-webkit-slider-thumb {
            appearance: none;
            width: 20px;
            height: 20px;
            background: #4CAF50;
            border-radius: 50%;
            cursor: pointer;
        }

        input[type="range"]::-moz-range-thumb {
            width: 20px;
            height: 20px;
            background: #4CAF50;
            border-radius: 50%;
            cursor: pointer;
        }

        /* Active Track */
        input[type="range"]:active {
            background: #4CAF50;
        }
    </style>
</head>
<body>
    <label for="volume">Volume:</label>
    <input type="range" id="volume" name="volume" min="0" max="100" value="50">
</body>
</html>

```

### 26. Focus & Active States  
- **`:focus`**: Styles applied when an element is focused.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Focus Example</title>
    <style>
        input {
            width: 200px;
            padding: 10px;
            border: 2px solid gray;
            outline: none;
        }

        input:focus {
            border-color: #4CAF50;
            box-shadow: 0 0 5px #4CAF50;
        }
    </style>
</head>
<body>
    <label for="name">Enter your name:</label>
    <input type="text" id="name" placeholder="Focus me">
</body>
</html>

```
- **`:active`**: Styles when an element is clicked.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Active Example</title>
    <style>
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #2196F3;
            color: white;
            border: none;
            cursor: pointer;
            transition: background 0.2s;
        }

        button:active {
            background-color: #0d8bf2;
            transform: scale(0.95);
        }
    </style>
</head>
<body>
    <button>Click Me</button>
</body>
</html>

```
- **`:disabled`**: Styles for disabled elements.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Disabled Example</title>
    <style>
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:disabled {
            background-color: gray;
            cursor: not-allowed;
            opacity: 0.5;
        }
    </style>
</head>
<body>
    <button disabled>Disabled Button</button>
</body>
</html>

```

### 27. Outline & Borders  
- **border-radius**: Rounds element corners. 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Border Radius Example</title>
    <style>
        .rounded-box {
            width: 200px;
            height: 100px;
            background-color: #4CAF50;
            color: white;
            text-align: center;
            line-height: 100px;
            border-radius: 20px;
        }
    </style>
</head>
<body>
    <div class="rounded-box">Rounded Box</div>
</body>
</html>

```
- **border-image**: Uses an image as a border. 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Border Image Example</title>
    <style>
        .image-border {
            width: 200px;
            height: 100px;
            text-align: center;
            line-height: 100px;
            border: 20px solid;
            border-image: url('https://via.placeholder.com/30') 30 round;
        }
    </style>
</head>
<body>
    <div class="image-border">Image Border</div>
</body>
</html>

``` 
- **outline**: Defines an outline outside the border. 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Outline Example</title>
    <style>
        .outlined-box {
            width: 200px;
            height: 100px;
            background-color: lightblue;
            text-align: center;
            line-height: 100px;
            border: 2px solid blue;
            outline: 5px dashed red;
        }
    </style>
</head>
<body>
    <div class="outlined-box">Outlined Box</div>
</body>
</html>

``` 

### 28. Hover Effects  
- **`:hover`**: Styles on mouse hover.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hover Example</title>
    <style>
        .hover-box {
            width: 200px;
            height: 100px;
            background-color: lightblue;
            text-align: center;
            line-height: 100px;
            transition: background-color 0.3s;
        }

        .hover-box:hover {
            background-color: coral;
            color: white;
        }
    </style>
</head>
<body>
    <div class="hover-box">Hover Over Me</div>
</body>
</html>

```
- **`:focus-within`**: Styles a parent when a child is focused.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Focus Within Example</title>
    <style>
        .focus-box {
            padding: 20px;
            border: 2px solid black;
            display: inline-block;
        }

        .focus-box:focus-within {
            border-color: green;
            background-color: lightyellow;
        }
    </style>
</head>
<body>
    <div class="focus-box">
        <label for="input">Click inside:</label>
        <input type="text" id="input">
    </div>
</body>
</html>

```
- **`:target`**: Styles an element targeted by a URL hash.  
 ```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Target Example</title>
    <style>
        .box {
            width: 200px;
            height: 100px;
            background-color: lightgray;
            text-align: center;
            line-height: 100px;
            margin: 20px;
        }

        #highlight:target {
            background-color: yellow;
            border: 2px solid red;
        }
    </style>
</head>
<body>
    <a href="#highlight">Click to Highlight</a>
    <div class="box">Box 1</div>
    <div class="box" id="highlight">Target Box</div>
    <div class="box">Box 3</div>
</body>
</html>

 ```
---

## Animations & Transitions  

### 29. CSS Transitions  
- **transition-property**: Specifies which property to animate.  
- **transition-duration**: Defines the time the transition takes.  
- **ease-in-out**: Smooth start and end.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Transitions Example</title>
    <style>
        .transition-button {
            background-color: royalblue;
            color: white;
            padding: 15px 30px;
            font-size: 16px;
            border: none;
            cursor: pointer;
            transition-property: background-color, transform;
            transition-duration: 0.5s;
            transition-timing-function: ease-in-out;
        }

        .transition-button:hover {
            background-color: crimson;
            transform: scale(1.2);
        }
    </style>
</head>
<body>
    <button class="transition-button">Hover Me</button>
</body>
</html>

```
 

### 30. CSS Animations  
- **@keyframes**: Defines animation steps.  
- **animation-name**: Assigns a name to the animation.  
- **animation-duration**: Defines how long the animation runs.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Animation Example</title>
    <style>
        /* Define the animation */
        @keyframes bounce {
            0% { transform: translateY(0); }
            50% { transform: translateY(-50px); }
            100% { transform: translateY(0); }
        }

        /* Apply the animation to the ball */
        .ball {
            width: 50px;
            height: 50px;
            background-color: crimson;
            border-radius: 50%;
            position: relative;
            animation-name: bounce;
            animation-duration: 1s;
            animation-iteration-count: infinite;
            animation-timing-function: ease-in-out;
        }
    </style>
</head>
<body>
    <div class="ball"></div>
</body>
</html>

```

### 31. Transformations  
- **rotate()**: Rotates an element.  
- **scale()**: Resizes an element.  
- **translate()**: Moves an element.  
- **skew()**: Skews an element.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Transform Example</title>
    <style>
        .container {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 50px;
        }

        .box {
            width: 100px;
            height: 100px;
            background-color: steelblue;
            color: white;
            font-size: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px solid black;
        }

        .rotate {
            transform: rotate(45deg);
        }

        .scale {
            transform: scale(1.5);
        }

        .translate {
            transform: translate(50px, 20px);
        }

        .skew {
            transform: skew(20deg, 10deg);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="box rotate">Rotate</div>
        <div class="box scale">Scale</div>
        <div class="box translate">Translate</div>
        <div class="box skew">Skew</div>
    </div>
</body>
</html>

```

### 32. Box & Text Shadows  
- **box-shadow**: Adds shadow to elements.  
- **text-shadow**: Adds shadow to text.  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Shadows Example</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            margin-top: 50px;
        }

        .box {
            width: 200px;
            height: 100px;
            background-color: steelblue;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            border-radius: 10px;
            margin: 20px auto;
            box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.3);
        }

        .text {
            font-size: 24px;
            font-weight: bold;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
        }
    </style>
</head>
<body>

    <div class="box">Box Shadow</div>
    <p class="text">Text Shadow Effect</p>

</body>
</html>

```
--- 

## Optimizations & Best Practices  

### 33.CSS Variables (`--var`)  
- Reusable and maintainable styles using `:root`.  
  ```css
  :root {
    --primary-color: #007bff;
    --font-size: 16px;
  }
  body {
    color: var(--primary-color);
    font-size: var(--font-size);
  }
  ```  

### 34.Minification & Performance  
- Remove unnecessary spaces, comments, and duplicate styles to improve load times.  
- Use tools like **CSSNano** or **PurgeCSS** to minimize CSS size.  

### 35.Preprocessors (SASS, LESS)  
- **Nesting**: Organizing styles hierarchically.  
- **Mixins**: Reusable style blocks.  
- **Functions**: Dynamic calculations in CSS.  
  ```scss
  $primary-color: #ff5733;
  body {
    color: $primary-color;
  }
  ```  

### 36. BEM Naming Convention  
- Scalable and maintainable CSS structure.  
  ```css
  .button { } /* Block */
  .button--primary { } /* Modifier */
  .button__icon { } /* Element */
  ```  

### 37. Normalize.css & CSS Resets  
- **Normalize.css**: Standardizes default browser styles.  
- **CSS Reset**: Removes default styles to provide a clean slate.  
  ```css
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  ```  

  ---

## Accessibility & Debugging  

### 37. CSS for Accessibility (a11y)  
- **Contrast**: Ensure sufficient color contrast for readability.  
- **Focus Indicators**: Improve keyboard navigation.  
  ```css
  button:focus {
    outline: 2px solid #007bff;
  }
  ```  
- **ARIA Attributes**: Help screen readers understand elements.  
  ```html
  <button aria-label="Submit Form">Submit</button>
  ```  

### 38.Debugging CSS  
- **Chrome DevTools & Firefox Inspector**: Inspect and modify styles in real time.  
- **Common Debugging Issues**:  
  - Unexpected margins → Use `outline: 1px solid red;` to visualize.  
  - Overflow issues → Check `overflow: hidden/auto;`.  
  - Specificity conflicts → Review CSS rules with `!important` cautiously.  

### 39. Quirks Mode & Browser Compatibility  
- **Quirks Mode**: Old browsers may render styles differently if `<!DOCTYPE html>` is missing.  
- **Vendor Prefixes**: Ensure cross-browser compatibility.  
  ```css
  .box {
    -webkit-border-radius: 10px;
       -moz-border-radius: 10px;
            border-radius: 10px;
  }
  ```  

### 40. External Stylesheets & Frameworks  
- **Bootstrap**: Prebuilt components and responsive grid system.  
- **Tailwind CSS**: Utility-first approach for rapid styling.  
  ```html
  <button class="bg-blue-500 text-white px-4 py-2 rounded">Click Me</button>
  ```  
  ---