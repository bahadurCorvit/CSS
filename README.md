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

### 21. Flexbox Advanced  
- **flex-grow**: Defines how much a flex item should grow.  
- **flex-shrink**: Determines how items shrink when necessary.  
- **align-self**: Aligns a single flex item differently from others.  

### 22. Gap Property (Grid & Flexbox)  
- Adds spacing between elements in Grid and Flexbox.  
  ```css
  .container {
    display: flex;
    gap: 20px;
  }
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
---

## Styling Forms & UI Components  

### 24. Buttons & Forms  
- **input, button, textarea, select**: Core form elements.  
  ```css
  input {
    padding: 10px;
    border: 1px solid #ccc;
  }
  ```  

### 25. Custom UI Elements  
- **Checkboxes & Radio Buttons**: Styled using `appearance` or pseudo-elements.  
- **Sliders**: Custom styles for `<input type="range">`.  
  ```css
  input[type="range"] {
    -webkit-appearance: none;
    width: 100%;
  }
  ```  

### 26. Focus & Active States  
- **`:focus`**: Styles applied when an element is focused.  
- **`:active`**: Styles when an element is clicked.  
- **`:disabled`**: Styles for disabled elements.  

### 27. Outline & Borders  
- **border-radius**: Rounds element corners.  
- **border-image**: Uses an image as a border.  
- **outline**: Defines an outline outside the border.  

### 28. Hover Effects  
- **`:hover`**: Styles on mouse hover.  
- **`:focus-within`**: Styles a parent when a child is focused.  
- **`:target`**: Styles an element targeted by a URL hash.  
  ```css
  button:hover {
    background-color: #007bff;
    color: white;
  }
  ```  
---

## Animations & Transitions  

### 29. CSS Transitions  
- **transition-property**: Specifies which property to animate.  
- **transition-duration**: Defines the time the transition takes.  
- **ease-in-out**: Smooth start and end.  
  ```css
  button {
    transition: background-color 0.3s ease-in-out;
  }
  button:hover {
    background-color: #ff5733;
  }
  ```  

### 30. CSS Animations  
- **@keyframes**: Defines animation steps.  
- **animation-name**: Assigns a name to the animation.  
- **animation-duration**: Defines how long the animation runs.  
  ```css
  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }
  .box {
    animation: fadeIn 1s ease-in-out;
  }
  ```  

### 31. Transformations  
- **rotate()**: Rotates an element.  
- **scale()**: Resizes an element.  
- **translate()**: Moves an element.  
- **skew()**: Skews an element.  
  ```css
  .box:hover {
    transform: scale(1.2) rotate(10deg);
  }
  ```  

### 32. Box & Text Shadows  
- **box-shadow**: Adds shadow to elements.  
- **text-shadow**: Adds shadow to text.  
  ```css
  .box {
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3);
  }
  .text {
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
  }
  ``` 
--- 