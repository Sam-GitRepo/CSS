## What is CSS?

- CSS stands for Cascading Style Sheets

- CSS describes how HTML elements are to be displayed on screen, paper, or in other media

- CSS saves a lot of work. It can control the layout of multiple web pages all at once

- External stylesheets are stored in CSS files

## CSS Syntax

- CSS is a collection of Rules

```html
<p>hello</p>
```

- to style the paragraph select p tag and add properties and values.

```css
p {
  color: yellow;
  text-align: cnter;
}
```

## CSS Selectors

A CSS selector selects the HTML element(s) you want to style.

We can divide CSS selectors into five categories:

- Simple selectors (select elements based on name, id, class)

```css
/*--------Class Selctor----*/
.classname {
}
/*---------id selector----*/
#IDname {
}
/*---------Tag-name-------*/
h1 {
}
div {
}
```

- Combinator selectors

  - select elements based on a specific relationship between them.

- Pseudo-class selectors

  - select elements based on a certain state

- Pseudo-elements selectors
  - select and style a part of an element.
- Attribute selectors
  - select elements based on an attribute or attribute value

## Three Ways to Insert CSS

There are three ways of inserting a style sheet:

- External CSS

```html
<head>
  <link rel="stylesheet" src="./style.css/" />
</head>
```

- Internal CSS

```html
<head>
  <style>
    #id1 {
      color: #123456;
      font-weight: 800;
    }
  </style>
</head>
```

- Inline CSS
  - it can override any style applied to this.

```html
<p style="color:blue;text-align:center">This is inline CSS</p>
```

# CSS Comments

Comments are used to explain the code, and may help when you edit the source code at a later date.

Comments are ignored by browsers.

```css
/*--------Comment---------*/
```

## Class And Id

- Both are ways to describe content.
- one class can have multiple tag.

```html
<p class="className"></p>
```

- One id has only one tag associated with that.

```html
<p id="Id1"></p>
```

## Inheritance tree

```html
<body>
  <h1>Head</h1>
  <div>
    <p>Text</p>
  </div>
</body>
```

- here if we cahnge the color of parent child then color of child will cahnge by default.

## Selector Specificity

```CSS
p{
    color:red;
}
p{
    color:white;/*this will be applied*/
}
```

- Specify the path

```CSS
#main p{
    color:red;/*This will win*/
}
p{
    color:white;
}
```

- How CSS Decides
  - ID 100 points
  - Classes 10 points
  - Elements 1 points

```html
<p class="c1" id="id1">Example</p>
```

```css
#id1 {
  color: red;
}
.c1 {
  color: white;
}
p {
  color: black;
}
```

- In the above case id has more specificity than other and styles of id is applied.

## !important

```CSS
#id1{
    color:red;
}
.c1{
    color:yellow !important;
}
```

- this time c1 will win because it use special declaration i.e. !important.

## Targetting Multiple element

```css
p,
span,
li,
a {
  color: black;
  font-size: 1.2rem;
}
```

## Decendent Selectors

```html
<main id="id1">
  <div class="div1">
    <p>Hello</p>
  </div>
  <p>Bye</p>
</main>
```

```CSS
#id1 .div1 p{
    color : green;
}

#id1 p{
    color:red;
}
```

## Children

```Html
<div class = "pd">
    <p>Direct Children-1</p>
    <p>Direct Children-2</p>
    <div>
        <p>Indirect Decendent</p>
    </div>
    <p>Direct Children-4</p>
</div>
```

```css
.pd > p {
  color: red;
}
```

## Adjecent Selector

- targets the element directly after the selector.

  ```html
  <div class="all-article">
    <h2>Artical-1</h2>
    <p>Hello I am adjecent</p>
    <p>I am Second adjecent</p>
    <p>I am third adject</p>
    <p>I am i am fourth</p>
  </div>
  ```

  ```CSS
  /*------Sectect first adjecent---*/
  .all-article h2 + p{
      color:red;
  }

  /*------Select second p tag---*/
  .all-artical h2 + p + p{
      color:blue;
  }

  /*----select such that all p after first    p----*/
  .all-article p + p{
      color:red;
  }
  ```

## Attribute Selectors

```html
<span>Hello i am span with no class</span>
<span class="c1">Hello i am span1-with class</span>
<span class="c2">Hello i am span1-with class</span>
<span class="c1">Hello i am span1-with class</span>
<span class="c1">Hello i am span1-with class</span>

<a href="hello.pdf">Hello pdf</a>
<a href="hello.txt">Hello txt</a>
<a href="hello.c">Hello c</a>
```

- select all span with class

```CSS
span[class]{
    color:blue;
}
```

- Select all with class c1

```css
span[class="c1"] {
  color: red;
}
```

- select a tag wth href with extension .pfd

```css
a[href$="pdf"] {
  color: red;
}
```
---
---

# Pseudo Selectors

- Special Keyword that go after selectors.
- They can be used to target.
  - special behavioral states
  - Advanced structural element.

## pseudo Class Groups

- Dynamic
- Structural
- Based on behaviour
- Advanced Structural

Eg: Hover effect

## Dynamic Pseudo Classes

Allow us to style element in relation to user action.

| `:hover` | `:active` | `:visited` |
| -------- | --------- | ---------- |

- Whether a link will have hover
- is Button pressed ?
- is checkbox is checked?

## Structural Pseudo classes

Allow us to style elements based on advanced structural techniques not possible from ordinary css selectors.

- The fifth <li\> tag from a list.
- A parent tag that has no children.

## : hover

- when cursor over then add styles.

```html
<div class="title">
  <h1>hellog G</h1>
</div>
```

- Add hover effrect to h1

```CSS
.title h1:hover{
    color:red;
}
```

## : active

- The :active CSS pseudo-class represents an element (such as a button) that is being activated by the user. When using a mouse, "activation" typically starts when the user presses down the primary mouse button.

```html
<a href="https://www.w3schools.com/css/css_colors.asp">W3 School</a>
```

- Change the color of link during click can be done using :active.

```css
a:active {
  color: white;
}
```

## : visited

Visited is used if you visited any thing then when you return back then it reminds that you visited this.

```html
<a href="https://www.w3schools.com/css/css_colors.asp">Visited</a>
```

- change the color of link after visiting

```css
a:visited {
  color: black;
}
```

## : first-child

it will apply styling on first child of any nested tags.

```html
<div>
  <!-first child--->
  <p>1-st</p>
  <p>2-nd</p>
  <p>3-rd</p>
</div>
```

- change color of first child

```css
div p:first-child {
  color: green;
}
```

## : last-child

it will apply styling on last child of any nested tags.

```html
<div>
  <p>1-st</p>
  <p>2-nd</p>
  <!-last child--->
  <p>3-rd</p>
</div>
```

- change last child color

```css
div p:last-child {
  color: red;
}
```

## : first-of-type

- it is a psedo selector to select first item from a content

```css
div p:first-of-type {
  color: greenyellow;
}
```

## : last-of-type

- to select last element

```css
article p:last-of-type {
  color: hotpink;
}
```

## : nth-child(n)

- where n can be

  - even -for position
  - odd
  - 1 to n
  - any formula like 2n + 1 or 3n + 1

- select 2nd tag

```css
ul li:nth-child(2) {
  color: green;
}
```

- select even-positioned tags

```css
ul li:nth-child(even) {
  color: pink;
}
```

- select odd-child tags

```css
ul li:nth-child(odd) {
  color: pink;
}
```

- select 2nd and 4th child

```CSS
ul li:nth-child(2),li:nth-child(4){
    color:black;
}
```

- select 2n+3 rd element

```css
ul li:nth-child(2n + 3) {
  color: pink;
}
```

## : nth-of-type(n)

- selects n th child of specific type

```css
article p:nth-of-type(1) {
  background: red;
}
```

# Pseudo element

## :: before

- before is a pseudo element used to add content before the content of any tag.
- in the below we have p tag ang we are adding some content before that .

```html
<p>I am Sam</p>
```

```css
p::before {
  content: "hello G ";
  color: green;
  font-size: 1.3rem;
}
```

Output will be : hello G I am Sam

## :: After

```html
<p>I am Sam</p>
```

```css
p::after {
  content: "hello G ";
  color: green;
  font-size: 1.3rem;
}
```

Output: I am Sam hello G


---
---

# CSS Positioning

## THE BOX MODEL

![layout](https://raw.githubusercontent.com/A-jha/CSS-LAB/master/Assets/layout1.jpg)

Every HTML element has a default display value, depending on what type of element it is.

There are two display values:

- block
- inline.

## INLINE ELEMENT

- An inline element does not start on a new line.

- An inline element only takes up as much width as necessary.

- This is a <span\> element inside a paragraph.

| Inline-Elements | Description                                                     |
| --------------- | --------------------------------------------------------------- |
| <a\>            | Defines a Hyperlink                                             |
| <abbr\>         | Defines an abbreviation or an acronym                           |
| <b\>            | defines bold text                                               |
| <bdo\>          | override the current text direction                             |
| <br\>           | single line break                                               |
| <button\>       | clickable button                                                |
| <cite\>         | Defines title of work                                           |
| <code\>         | Defines piece of computer code                                  |
| <dfn\>          | Specifies a term that is going to be defined within the content |
| <em\>           | Defines emphasized text                                         |
| <i\>            | Defines a part of text in an alternate voice or mood            |
| <img\>          | Defines an image                                                |
| <input\>        | Defines an input control                                        |
| <kbd\>          | Defines keyboard input                                          |
| <label\>        | Defines a label for an <input\> element                         |
| <map\>          | Defines an image map                                            |
| <object\>       | Defines a container for an external application                 |
| <output\>       | Defines the result of a calculation                             |
| <q\>            | Defines a short quotation                                       |
| <samp\>         | Defines sample output from a computer program                   |
| <script\>       | Defines a client-side script                                    |
| <select\>       | Defines a drop-down list Defines a specific time (or datetime)  |
| <small\>        | Defines smaller text                                            |
| <span\>         | Defines a section in a document                                 |
| <strong\>       | Defines important text                                          |
| <sub\>          | Defines subscripted text                                        |
| <sup\>          | Defines superscripted text                                      |
| <textarea\>     | Defines a multiline input control (text area)                   |
| <time\>         | Defines a specific time (or datetime)                           |
| <var\>          | Defines a variable                                              |

## BLOCK LEVEL ELEMENT

- A block-level element always starts on a new line.

- A block-level element always takes up the full width available (stretches out to the left and right as far as it can).

- A block level element has a top and a bottom margin, whereas an inline element does not.

| Block-level-Element | Description                                                                    |
| ------------------- | ------------------------------------------------------------------------------ |
| <address\>          | Defines contact information for the author/owner of a document                 |
| <article\>          | Defines an article                                                             |
| <aside\>            | Defines content aside from the page content                                    |
| <blockquote\>       | Defines a section that is quoted from another source                           |
| <canvas\>           | Used to draw graphics, on the fly, via scripting (usually JavaScript)          |
| <dd\>               | Defines a description/value of a term in a description list                    |
| <div\>              | Defines a section in a document                                                |
| <dl\>               | Defines a description list                                                     |
| <dt\>               | Defines a term/name in a description list                                      |
| <fieldset\>         | Groups related elements in a form                                              |
| <figcaption\>       | Defines a caption for a <figure\> element                                      |
| <figure\>           | Specifies self-contained content                                               |
| <footer\>           | Defines a footer for a document or section                                     |
| <form\>             | Defines an HTML form for user input                                            |
| <h1\>-<h6\>         | Defines HTML headings                                                          |
| <header\>           | Defines a header for a document or section                                     |
| <hr\>               | Defines a thematic change in the content                                       |
| <li\>               | Defines a list item                                                            |
| <main\>             | Specifies the main content of a document                                       |
| <nav\>              | Defines navigation links                                                       |
| <noscript\>         | Defines an alternate content for users that do not support client-side scripts |
| <ol\>               | Defines an ordered list                                                        |
| <p\>                | Defines a paragraph                                                            |
| <pre\>              | Defines preformatted text                                                      |
| <section\>          | Defines a section in a document                                                |
| <table\>            | Defines a table                                                                |
| <tfoot\>            | Groups the footer content in a table                                           |
| <ul\>               | Defines an unordered list                                                      |
| <video\>            | Defines embedded video content                                                 |
---
---
# FLEX BOX

![basic-term](https://raw.githubusercontent.com/A-jha/CSS-LAB/master/Assets/00-basic-terminology.svg)

- Apply a display type of flex to parent container.

## Benifits of flex box

- Navigation Bar & Menus
- Grid Layout
- Bar Chart
- Equal height column

# CSS Flex Container

### Parent Element (Container)

![display-flex](https://github.com/A-jha/CSS-LAB/raw/master/Assets/display-flex.svg)

## Flex Container Properties

- ### flex-direction
  - Specifies the direction of the **flexible items** inside a flex container
- ### flex-wrap
  - Specifies whether the flex items should wrap or not, if there is not enough room for them on one flex line
- ### flex-flow
  - A shorthand property for flex-direction and flex-wrap
- ### justify-content
  - Horizontally aligns the flex items when the items do not use all available space on the main-axis
- ### align-items
  - Vertically aligns the flex items when the items do not use all available space on the cross-axis
- ### align-content
  - Modifies the behavior of the flex-wrap property. It is similar to align-items, but instead of aligning flex items, it aligns flex lines

## flex-direction

The flex-direction property defines in which direction the container wants to stack the flex items.

### Flex direction can be of ":

- column
- column-reverse
- row
- row-reverse

![ex](https://github.com/A-jha/CSS-LAB/raw/master/Assets/cont-1.svg)

## flex-wrap

**What is wrap ?**

The flex-wrap CSS property sets whether flex items are forced onto one line or can wrap onto multiple lines. If wrapping is allowed, it sets the direction that lines are stacked.

### Properties included in flex wrap:

- wrap
- wrap-reverse
- nowrap

![flex-wrap](https://github.com/A-jha/CSS-LAB/raw/master/Assets/flex-wrap.png)

## flex-flow

The flex-flow property is a shorthand property for setting both the flex-direction and flex-wrap properties.

```CSS
.container{
    display:flex;
    flex-flow:row wrap;
}
```

## justify-content

The justify-content property is used to align the flex items.

- center
- flex-start
- flex-end
- space-around
- space-between

![justify-content](https://github.com/A-jha/CSS-LAB/raw/master/Assets/justify-content.svg)

## align-item

The align-items property is used to align the flex items.

- center
- flex-start
- flex-end
- stretch
- baseline

![align-items](https://github.com/A-jha/CSS-LAB/raw/master/Assets/align-items.svg)

## Align Content

The align-content property is used to align the flex lines.

![align-content](https://github.com/A-jha/CSS-LAB/raw/master/Assets/align-content.svg)

# CSS Flex Items

The direct child elements of a flex container automatically becomes flexible (flex) items.

## The flex item properties are:

- ### order
  - Specifies the order of the flex items inside the same container
- ### flex-grow
  - Specifies how much a flex item will grow relative to the rest of the flex items inside the same container
- ### flex-shrink
  - Specifies how much a flex item will shrink relative to the rest of the flex items inside the same container
- ### flex-basis
  - Specifies the initial length of a flex item
- ### flex
  - A shorthand property for the flex-grow, flex-shrink, and the flex-basis properties
- ### align-self
  - Specifies the alignment for a flex item (overrides the flex container's align-items property)

## The order Property

The order property specifies the order of the flex items.

- The first flex item in the code does not have to appear as the first item in the layout.

- The order value must be a number, default value is 0.

- order is a comparision between each child and according to that positioned.

![order](https://github.com/A-jha/CSS-LAB/raw/master/Assets/order.svg)

## Flex Grow

The flex-grow property specifies how much a flex item will grow **relative** to the rest of the flex items.

- The value must be a number, default value is 0.

```
 if total width is 100 and we have 3 item
 item-1 flex-2
 item-2 flex-4
 item-3 dlex-2

 then width of item-1 (2 * 100)/8 = 25%
 then width of item-2 (4 * 100)/8 = 50%
 then width of item-3 (2 * 100)/8 = 25%
```

## flex-shrink

The flex-shrink property specifies how much a flex item will shrink **relative** to the rest of the flex items.

The value must be a number, default value is 1.

- if flex-shrink = 0 then the item will not shrink.

## flex-basis

The flex-basis property specifies the initial length of a flex item.

- if length is not change later then it will be of the flex-basis size always.

## flex

The flex property is a shorthand property for the `flex-grow`, `flex-shrink`, and `flex-basis` properties.

## align-self

The align-self property specifies the alignment for the selected item inside the flexible container.

The align-self property overrides the default alignment set by the container's align-items property.

---

---
 
---