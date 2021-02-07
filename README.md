# Complete guide of CSS

Repo for learning css from basic to advance

## 1. BASIC GUIDES

### 1.1. FONT-FAMILY: Changing the font-family of the text node

Following the guide of the fonts page of google fonts:

<https://fonts.google.com/>

```html
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap"
  rel="stylesheet"
/>

...
<style>
  h1 {
    font-family: "Roboto", sans-serif;
  }
</style>
<style>
  h1 {
    font-family: inherit;
  }
</style>
```

### 1.2. COMBINATORS: Type of combinators (Adjacent, General, Child, Descendant)

ADJACENT: p that following by h2 tag will be applied

```css
h2 + p {
  color: red;
}
```

GENERAL: p that having h2 with the same level will be applied

```css
h2 ~ p {
  color: red;
}
```

CHILD: p that are directed child of div will be applied

```css
div > p {
  color: red;
}
```

DESCENDANT: p is a descendant of the div (not care of which level)

```css
div p {
  color: red;
}
```

### 1.3 BOX-MODEL: The basic approach

Every element in html will be understand as a box inside CSS (in debug)

#### 1.3.1. The default margin 8px of body tag

The body tag having the default margin of 8

```css
body {
  margin: 0;
}
```

#### 1.3.2. Margin Collapsing

The margin bigger of element will cover the other -> this is a css features

#### 1.3.3. Shorthand properties

Combine values of multiple props in a single property

```css
/* Normal way */
body {
  border-width: 2px;
  border-style: dashed | solid;
  border-color: orange;
}
/* Shorthand way */
body {
  border: 2px dashed orange;
}

body {
  margin: 5px 10px 5px 10px; /* top right bottom left */
  margin: 5px 10px; /* top + bottom lef + right */
}
```

#### 1.3.4. HEIGHT & WIDTH: Cool trick to set height of element

We'll learn other dimension and measure unit but in here just remember:

1. The child element get height % with the parent.
2. So set height of html tag -> body tag -> parent -> child to 100% to get full page width.

THE CONTENT BOX: the default box-sizing of element -> if set width: 100% and set padding border and margin -> the total will exceed the width.

-> To solve this we should set the box-sizing to border-box:

```css
div {
  width: 100%;
  height: 528px;
  padding: 10px;
  border: 5px solid black;
  box-sizing: border-box;
}
```

> Margin should not be part of the height and width.

We could override the default to border-box with universal selector:

```css
* {
  box-sizing: border-box;
}
```

#### 1.3.5. DISPLAY PROPERTY: config the display of element

inline-block: display inline but still behave like block element when setting TOP & BOTTOM. Sit inline but style like block.

vertical-align: set in both inline-block elements to get them middle.

calc(100% - ?px)

#### 1.3.6. PSEUDO: Pseudo class and Pseudo elements

CLASS: Defines the style of a special state of an element (:classname)
<https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes>
ELEMENT: Defines the style of a specific part of an element (::elementname)
<https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements>

Example of pseudo class and element:

```css
.main-nav__item a::after {
  content: " (Link)";
  color: red;
}

p::first-letter {
  color: red;
}
```

GROUPING RULES:

```css
.main-nav__item a:hover,
.main-nav__item a:active {
  color: white;
}
```

### 1.4. MORE ON SELECTORS

#### 1.4.1. More on CSS Class

```css
/* Select the a tag with class of active */
a.active {
}
```

#### 1.4.2. The :not() pseudo class

<https://developer.mozilla.org/en-US/docs/Web/CSS/:not>

```css
a:not(.active) {
  color: blue;
}
```

#### 1.4.3. The box-shadow property

For dropping shadow on the element

```css
.plan-highlighted {
  box-shadow: 2px 2px 2px 2px rgba(0, 0, 0, 0.205);
}
```

#### 1.4.4. Basic sample to set up css for button

```css
.button {
  background-color: #0e4f1f;
  color: white;
  font: inherit;
  border: 1.5px solid #0e4f1f;
  padding: 8px;
  border-radius: 8px;
  font-weight: bold;
  cursor: pointer;
}

.button:hover,
.button:active {
  color: #0e4f1f;
  background: white;
}

.button:focus {
  outline: none;
}
```

#### 1.4.5. Outline of the default browser

The default wrapper of browser (not include in the box model)
In the button, we can check that in the focus state.

```css
.button:focus {
  outline: none;
}
```

### 1.5. The float and clearfix for fixing the float (the following element)

The float will remove the element from the dom display -> the next el will overflow to the place the element has left.

-> using clearfix to fix the float problem.

### 1.6. Fixing the border-left when using in id selector

The best practice is to define the new border-left-color in hover and active instead of using !important

```css
#free:hover,
#free:active {
  border-left-color: #ff5454;
}
```

### 1.4. POSITIONING

#### 1.4.1.
