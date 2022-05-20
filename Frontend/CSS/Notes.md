# **CSS**

Cascading Style Sheets

## **Power of CSS**

HTML defines content but the styling provided by CSS makes the content much
 easier to digest. Content should be displayed in a manner that is convenient
 and pleasant to the consumer. CSS provides a system to update the style of HTML
 content.

## **Anatomy of CSS**

CSS works by associating rules with HTML elements.
Selector "p" is followed by {} which contains the CSS declaration containing
 property and values.

```CSS
p {
    color: blue;
    font-size: 20px;
    width: 20px
}

h1 {
    color: green;
    font-size: 36px;
    text-align: center;
}
```

CSS is organied in a stylesheet as above. Where each HTML element by defaulty
 tag or specified id is referenced in a single space.

## **Types of Selectors**

Element selector: Every element with the specified tag will be styled by this
 style. See p and h1 above.

There is also a class selector which can be linked to specific class declartions
 in HTML.

```CSS
.blue {
    color: blue;
}
```

Will be attached to

```html
<p class="blue">...</p>
<div class="blue">...</div>
```

And the other common selector is the id selector. This will be the most
 restrictive as ids will need to be unique for Javascript use cases.

```CSS
#name {
    color="blue"
}
```

```html
<div id="name">...</div>
```

CSS Selectors can also be grouped using commas

```css
div, .blue {
    color: blue;
}
```

## **Combining Selectors**

Element with class selector

This will select every p element with the class big assigned.

```css
p.big {
    font-size: 20px
}
```

easier to digest. Content should be displayed in a manner that is convenient and pleasant to the consumer. CSS provides a system to update the style of HTML content.

```css
child > p {
    color: blue;
}
```

```html
<!-- Affected -->

<article>
    <p>Affected</p>
</article>

<!-- Unaffected -->

<p>Unaffected</p>

<article>Unaffected</article>

<article>
    <div>
        <p>Unaffected</p>
    </div>
</article>
```

### **Descendant Selector**

This one functions similar to the Child selector accept it also allows the last
 case and any amount of nesting between the elements is stylized

```css
article p {
    color: blue;
}
```

```html
<!-- Affected -->

<article>
    <p>Affected</p>
</article>

<article>
    <div>
        <p>Affected</p>
    </div>
</article>

<!-- Unaffected -->

<p>Unaffected</p>

<article>Unaffected</article>

<p>
    <article>
        Unaffected
    </article>
</p>
```

### **Psuedo Class Selector**

There are many pseudoclass selectors. These are some of the mopst common ones

* :link
* :visited
* :hover
* :active
* :nth-child(...)

A pseudo-class selector is declared using an existing selector and adding the
 above to end of the class selector.

```css
p:visited {
    color: red;
}

p.highlight:active {
    color: green;
}

article p:hover {
    color: purple;
}
```

## **CSS Placement**

Style can be placed within the stylesheet which can be accessesd using the link
 tag in the header.

```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

In the style blocks. Which we have been using up until this point.

```html
<style>
    p {
        color: red;
    }
</style>
```

Or directly on the attribute they are styling. (In-Line)

```html
<p style="background-color: yellow;">This will be highlighted in yellow</p>
```

In-Line styling is the least preferred and should only be used in specific cases
 or for testing things out.

External style sheets are preferred because they can be referenced to multiple
 pages and used across multiple pages of the same web site.

## **Conflict Resolution**

Cascading is a fundamental feature of CSS. The cascade algotrithm is at the
 source of CSS.

4 Concepts:

* [Origin](###Origin)
* [Merge](###Merge)
* [Inheritance](###Inheritance)
* [Specificity](###Specificity)

### **Origin**

Simple Rule -- Last declaration wins

This is determined from top to bottom through HTML. External CSS is declared
 where-ever the CSS was declared. (cat style.css) directly where it is called.

### **Merge**

If there are different rules (color and font-size) but they are declared at
 different locations. These declarations will merge and the text will take both
 properties. If the same property is redeclared the most recent declaration will
 override.

### **Inheritance**

All Children of a specified element will inherit that property.

```text
  A
 / \
B   C
   / \
  D   E
```

If a style is declared on A then B, C, D, and E will inherit that trait. If it
 is declared at C then only C, D and E would display the trait.

```css
body {
    color: blue;
}
```

The body element is an obvious place to declare this if we wish for certain
 styles to apply to all elements on the page.

### **Specificity**

Most specific selector combination wins.

Style elements applied directly to the html via style attribute. This will
 always win.

The ID is the next most specific, followed by class, pseudo-class, and
 attributes.

Finally the number of elements in the selector makes the last number.

This could be looked at by looking at the values supplied.

| Style | ID | Class | Count |
|:-----:|:--:|:-----:|:-----:|
|0      |0   |0      |0      |

When tallying the above metrics whichever produces the largest number (After
 adjusting the base to maximum number shown) is the most "Specific"

## **Styling**

```css
.style {
    text-transform: uppercase;
    font-weight: bold;
    font-style: italic;
    font-family: Arial, Helvetica, sans-serif;
    text-align: center;
}
```

Plus many many more.
Font size uses multiple options but a good standard is px. px stands for pixels
 and is considered a standard sizing. On small displays they may translate into
 literal pixels but on higher resolution they will scaled using DPI.

### **Relative Font Sizing**

Fonts can be sized via percentage where they will use the default font-size and
 multiply it by the % provided.

```css
body {
    font-size: 120%;
}
```

```css
p {
    font-size: 2em;
}
```

2em here multiplies the provided font by 2. Font-size is cumulative. 2em applied
 over a 120% will be 240% the default font-size.

## **Box Model + Layout**

In HTML every element is considered a box.

The box consists of content, border, margin, and padding.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>The Box Model</title>
        <style>
            body {
                background-color: gray;
            }
            #box {
                background-color: blue;
            }
            #content {
                background-color: green;
            }
            h1 {
                margin-bottom: 30px;
            }
        </style>
    </head>
    <body>
        <h1>Box Model</h1>
        <div id="box">
            <div id="content">
                Lorem Ipsum Dolor
            </div>
        </div>
    </body>
</html>
```

Default Layout Above -- Modified to show the values of each position Below

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>The Box Model</title>
        <style>
            /* Star Selector selects every element and adds this code to it */
            * {
                /*box-sizing border width will make any numbered width value
                provided match to the entire box size as opposed to just
                the content */
                box-sizing: border-box;
            }
            body {
                /* This overwrites the default margin provided by the browser */
                margin: 0px;
                padding: 0px;
                background-color: gray;

            }
            #box {
                background-color: blue;
                /* This adds spacing around the internal box to distinguish 
                them */
                padding: 10px;
                border: 3px solid black;
                margin: 40px;
                /* Fit Content will automatically scale the container so any 
                content will fit */
                width: fit-content;
            }
            #content {
                background-color: green;
            }
            h1 {
                margin-bottom: 30px;
            }
        </style>
    </head>
    <body>
        <h1>Box Model</h1>
        <div id="box">
            <div id="content">
                Lorem Ipsum Dolor
            </div>
        </div>
    </body>
</html>
```

Margins are cumulative for (Right + Left). For (Bottom + Top) the larger element
wins.

### Overflow

```html
<style>
    #box {
        overflow: ;
    }
</style>
```

There are a number of commands for overflow and they handle different cases when
the content size ends up being larger than the box containing it.

* auto: Adds a scroll bar
* default is visible
* hidden: clips at end of box
* scroll: will provide a constant scroll bar even if there is no need
