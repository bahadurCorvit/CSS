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

---
## Text & Colors

### 6. Typography  
- **font-family**: Defines the typeface of text.  
- **font-size**: Specifies the size of the text.  
- **line-height**: Controls the spacing between lines of text.  
- **letter-spacing**: Adjusts the space between characters.  

### 7.  Color & Backgrounds  
- **rgb, rgba**: Defines colors using red, green, blue (with optional alpha for transparency).  
- **hsl**: Defines colors using hue, saturation, and lightness.  
- **hex**: Specifies colors using hexadecimal values.  
- **background-image**: Sets an image as the background of an element.  

### 8. Lists & Tables  
- **list-style**: Controls the appearance of list markers.  
- **border-collapse**: Specifies whether table borders should collapse into a single border.  
- **border-spacing**: Defines the space between table borders.  

### 9. White Space & Hyphenation  
- **white-space**: Controls how white space is handled in elements.  
- **hyphens**: Manages word hyphenation behavior.
---

## Layout Fundamentals  

### 10.  Display Property  
- **block**: Elements take up the full width available.  
- **inline**: Elements only take up as much width as necessary.  
- **inline-block**: Like inline but allows setting width and height.  
- **none**: Hides the element completely.  

### 11. Positioning  
- **static**: Default positioning (follows normal document flow).  
- **relative**: Positioned relative to its normal position.  
- **absolute**: Positioned relative to the nearest positioned ancestor.  
- **fixed**: Stays fixed relative to the viewport.  
- **sticky**: Toggles between relative and fixed based on scroll position.  

### 12. Flexbox Basics  
- **display: flex**: Enables flexbox layout.  
- **flex-direction**: Defines the main axis (`row`, `column`).  
- **justify-content**: Aligns items along the main axis.  
- **align-items**: Aligns items along the cross axis.  

### 13. CSS Grid Basics  
- **grid-template-columns**: Defines the number and size of columns.  
- **grid-template-rows**: Defines the number and size of rows.  
- **gap**: Sets spacing between grid items.  

### 14. Float & Clear (Legacy)  
- **float**: Allows elements to be positioned to the left or right.  
- **clear**: Prevents elements from wrapping around floated elements.  

---
## Responsive Design & Media Queries  

### 15. Media Queries  
- **@media**: Applies styles based on different screen sizes.  
  - Example:  
    ```css
    @media (max-width: 768px) {
      body {
        background-color: lightgray;
      }
    }
    ```  

### 16. Viewport Units  
- **vh (Viewport Height)**: Percentage of the viewport height.  
- **vw (Viewport Width)**: Percentage of the viewport width.  
- **vmin**: Smaller value of `vh` or `vw`.  
- **vmax**: Larger value of `vh` or `vw`.  

### 17. Aspect Ratio  
- **aspect-ratio**: Maintains element proportions.  
  - Example:  
    ```css
    .box {
      width: 50%;
      aspect-ratio: 16 / 9;
    }
    ```  

### 18. Overflow & Scroll Behavior  
- **overflow**: Controls content overflow (`visible`, `hidden`, `scroll`, `auto`).  
- **scroll-behavior**: Defines how scrolling happens (`auto`, `smooth`).  

### 19. Mobile-First & Adaptive Layouts  
- **Mobile-First Approach**: Designing for mobile first and scaling up for larger screens.  
- **Adaptive Layouts**: Using breakpoints to adjust designs for different devices.  
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