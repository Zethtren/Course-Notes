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

### **Overflow**

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

### **Backgrounds**

There are a number of background properties that can be used when coding CSS.
"background-image: <>;" This will accept relative URLS when relative to the CSS
file. You can also use an absolute path to a web url. Default behaviour is
repeat. "background-repeat" will allow you to select only x or y repeat or
"no-repeat". "background-position" can let you place the image in a relative
position. It will default to center if only one axis is provided. you can also
use the "background" property.

```css
#bg {
    background: url('some.png') no-repeat right center;
}
```

"background" when used this way will overwrite "background-color". You can
simply tack a color in to specify a color.

```css
#bg{
    background: url('some.png') no-repeat right center #0000FF;
}
```

Background property is great for position elements based on screen-size.

## **Positioning Schemes**

### **Static**

Default.

### **Floating**

Most modern web-pages are designed with floating. Floationg allows you to
arrange items on the screen in any desired fashion. Floating is moved outside
of the normal document context. If you do not "clear" your next non-floating
element, then html will render that content behind your floating content.

* [Floating](./lecture_21/floating.html)
* [Two Column Design](./lecture_21/two-column-design.html)

### **Relative**

```css
p {
    position:   relative;
    top:        50px;
    left:       50px; /*This is measurement from the top left point */
}
```

All offsets are measured to the nearest neighbor with non-static position.
&lt;html> is the only element that is non-static by default. It is automatically
rendered to "relative". Elements set to Absolute are removed from document flow.
Items offest inside a container will inherit offsetting from the parent element
If the parent element is shifted then the children will be shifted as well by
the same amount.

Some confusion can be caused in the case of sibling elements. In the example
provided you can see that the html renderer still treats elements p2 - p4 as if
element p1 was rendered in its original placement even though it has been
shifted.

[Relative Postioning Example](./lecture_22/relative-example.html)

```css
    * {
        box-sizing: border-box;
    }
    div {
        background-color: blanchedalmond;
        color: black;
    }
    p {
        width: 50px;
        height: 50px;
        border: 2px solid black;
        margin: 5px;
    }
    #p1 {
        background-color: darkkhaki;
        position: relative;
        top: 55px;
        left: 55px;
    }
    #p2 {
        background-color: lightsalmon;
    }
    #p3 {
        background-color: lightslategrey;
    }
    #p4 {
        background-color: coral;
    }
```

### **Absolute**

There are a few key concepts about Absolute positioning of Elements.

* Elements will be placed based on the closest parent element with relative
positioning. Which is &lt;html&gt; by default.
* Setting an element to absolute will remove it from the page flow.
  * Any sibling elements will ignore it in their positioning.

Moving box 3 using absolute position will show a couple of unique problems.

```css
    * {
        box-sizing: border-box;
    }
    div {
        background-color: blanchedalmond;
        color: black;
    }
    p {
        width: 50px;
        height: 50px;
        border: 2px solid black;
        margin: 5px;
    }
    #p1 {
        background-color: darkkhaki;
        position: relative;
        top: 55px;
        left: 55px;
    }
    #p2 {
        background-color: lightsalmon;
    }
    #p3 {
        background-color: lightslategrey;
        position: absolute;
        left: 0px;
        top: 0px;
    }
    #p4 {
        background-color: coral;
    }
```

[Rendered Here](./lecture_22/absolute-example.html)

As you can see the box p3 gets moved based on the &lt;html&gt; tag as opposed to
the expected container as p1 did. On top of that, p4 will now render as if p3 is
no longer there. Remember absolute elements are ignored in relative element
placements. The absolute element will be rendered to the nearest parenting
"relative positioned" element. Which by default is &lt;html&gt;. We can create a
relative positioning argument for the containing div box and the behaviour will
be closer to what is expected.

[Updated Example](./lecture_22/absolute-container-example.html)

```css
    div#container {
        position: relative;
    }
```

```html
<div id="container">
    <p id="p1"></p>
    <p id="p2"></p>
    <p id="p3"></p>
    <p id="p4"></p>
    <section>
        This is a regular section continuing after the paragraph blocks.
    </section>
</div>
```

You can move this container as whole and all thew contained elements will move
with it.

```css
    div#container {
        position: relative;
        top: 25px;
    }
```

## **Responsive Design**

### **Media Queries**

Media queries allow for dynamically adjusting the style of a page based on
attributes of the device used to view it. Media queries start with the key-word
"@media" and "()". Attributes are evaluated within the parenthesis. If they
evaluate to true, then the contents of the media query are applied to any
contained elements.

```css
@media (max-width: 767px) {
    p {
        color: blue;
    }
}
```

Example query items include:

* max-width (max-width: 800px)
* min-width (min-width: 800px)
* orientation (orientation: portrait)
* screen
* print

Features can be combined using logical operators and additional parens

```css
@media (min-width: 768px) and (max-width: 991px) {...}
@media (max-width: 768px) , (min-width: 991px) {...} 
/* , represents or */
```

min and max width are always inclusive so it is advised to provide at least one
value of difference when prepping multiple device styles.

```css
@media (min-width: 768px) and (max-width: 991px) {...}
@media (min-width: 992px) {...} 
/* If they were both set to 992 then both styles would be applied */
/* This could have unexpected consequences and can be difficult to maintain*/
```

Sample of basic responsiveness can be seen here:\
[Example Media Query](./lecture_23/media-queries.html)

### **Responsive Design Layout**

Born from the necessity to handle the growth of mobile devices for browsing the
internet. Since late 2013 there are more mobile browsers than desktop browsers.
Whenever possible it is best to design your website to respond to ALL devices.
A responsive website is defined as such: "Site designed to adapt to the viewing
environment by using fluid proportion-based grids, flexible images, and CSS3
media queries". ***Yaakov Chaikin***
[Link to source](https://www.coursera.org/learn/html-css-javascript-for-web-developers/lecture/Pfa75/lecture-24-part-1-responsive-design)
at 1:28 timemark. Some parts of the site may be hidden when designing for mobile
because ther emay not be enough space to display the content. The alternative is
to use a server to identify devices and then serve different versions of the
website by the server. This is no longer practical due to large variation in
mobile device and desktops.

Most responsive frameworks will use a 12 column grid because it easily divisible
by 2, 3, 4, and 6 which should allow for most common design schemas. 1 column
represents 8.33% of the page. It is also possible to nest another 12 column grid
within any number individual or grouped columns of the main layout.

[Example Responsive Design Layout](./lecture_24/responsive.html)

### **Twitter Bootstrap**

<span style="color: white; background-color: darkred">

Bootstrap was designed by Twitter and is the most popular HTML, CSS and JS
framework for designing responsive web-pages. Bootstrap is mostly CSS. Designing
mobile first is the most common design paradigm. Unless the web-page would be
too cluttered or impossible to use on mobile this is the recommended design.

</span>

<span style="color: white; background-color: darkred">

The number one complaint for bootstrap is that is too bloated. You can download
small portions of the bootstrap framework instead of the entire package.
However, it is actually not *too* bloated and the entire package can be
transported relatively easily.

</span>

<span style="color: white; background-color: darkred">

For the time being I installed bootstrap via

</span>

```bash
wget -o bootstrap.zip "https://github.com/twbs/bootstrap/releases/download/v3.4.1/bootstrap-3.4.1-dist.zip"
unzip bootstrap-3.4.1-dist.zip
```

***This Course has been using Bootstrap 3 and doesn't appear to be compatible
with bootstrap 5.x*** Because of this I will briefly detour to a youtube video
and notate based on modern implementations.

[Link to Youtube Video](https://www.youtube.com/watch?v=-qfEOE4vtxE)

Currently Bootstrap is used in over 20% of websites (2021) and 71% of framework
market share.

Bootstrap is fast, responsive, has few dependencies now, is largely customizable
and has a huge support community.
