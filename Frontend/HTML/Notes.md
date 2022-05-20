# **HTML + CSS + JS**

Having a solid Frontend is paramount to the success of a business.

Even if everything works perfectly in the backend. If the frontend experience is lackluster than the project will likely fail due to lack of adoption.


## **HTML CSS and JS**

* HTML supplies structure
* CSS supplies the style
* Javascript supplies behaviour

## **HTML History**

Prior to 1997 there were no standards in web development. At 1997 HTML 4.0 became the standard but there were still discrepencies in implimentation. 2000 XHTML 1.0 came out and was based on XML. Browser vendors decided that web development was moving in the wrong direction. Developers banded together and produced WHATWG HTML. 1 Editor was appointed to make all final decisions surrounding the development of HTML 5.0 and now there is a strong sense of congruency in HTML. 2007 W3C and WHATWG work together and finalized a decision to move forward with HTML 5.0.

W3C is in charge of current standard (HTML 5.0). WHATWG is in charge of browser and HTML evolution. W3C cherry picks from the recent developments by WHATWG and sets the standard. Browsers perform silent updates and this allows most recent webpage options.

* [w3c](www.w3.org/TR/HTML)
* [CanIUse](caniuse.com)
* [Validator](https://validator.w3.org/#validate_by_upload)
* [Browser Use stats](www.w3schools.com/browsers/browsers_stats.asp)

## **Anatomy of HTML Tag**

Usually HTML will have an opening and closing tag that surround content.
There is an opening tag, closing tag and the content they surround

```html
<p>TEXT</p>
```

The closing tag should match the opening tag. However there examples which only have opening tags

```html
<hr> and <br> signify page breaks and line-breaks and operate as a single insert.
```

You can use predefined attributes on tags

```html
<p id="myId"></p>
```

* No space can exist between the opening bracket "<" and the tag type "p"
* No space can exist between the opening bracket "<" and tag close "/p"
* A single space must exist between the tag type "p" and the attribute "id"
* All other spaces are allowed and simply ignored
* Attributes can only be specified on the opening tag

## **Basic HTML document structure**

DOCTYPE declarations is largely historical. Using this header ensures that the browser parses the page as modern HTML 5.0

HTML is rendered sequentially from top to bottom.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>This is required and is what is displayed on the browser tab</title>
    </head>
    <body>
    </body>
</html>
```

## **Div and Span**

Div is most generic block element
Span is the most generic inline element

Since div requires that content within is in its own block
Therefore a span existing outside of Div will be pushed to a new line.
Since Span is an inline element when it is used inside a block element it will exist in the same line.

## **Essential HTML Tags**

### **Heading Elements**

```html
<h1>This is the main heading</h1>
<h2></h2>
<h3></h3>
<h4></h4>
<h5></h5>
<h6></h6>
```

H1 is largest and H6 is the smallest. This is similar to markdown 

```markdown
#
##
###
####
#####
######
```

### **Semantic Elements**

Tells you something about the content.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Heading Elements</title>
    </head>
    <body>
        <header>
            Header Element - Some header information goes here. Usually consists of company logo, some tag line, etc. Sometimes Navigation is contained in the header as well.
            <nav>
                Nav -- Short for Navigation -- Usually contains links to different parts of the same website
            </nav>
        </header>
        <h1>
            Main heading of the page (Should almost always be present in some form)
        </h1>
        <section>
            Section 1
            <article>Article 1</article>
            <article>Article 2</article>
            <article>Article 3</article>
        </section>
        <section>
            Section 2
            <article>Article 4</article>
            <article>Article 5</article>
            <article>Article 6</article>
            <div>
                Regular DIV element
            </div>
        </section>
        <aside>
            ASIDE -- Some information that relates to the main topic. i.e. related posts.
        </aside>
        <footer>
            FOOTER Content
        </footer>
    </body>
</html>
```

Section, Article, Footer, Header, and Div all basically do the same thing. It just makes the HTML more human readable. It easier to gather context when reading or modifying the source code of your page.

### **Lists**

This is an example displaying listed content without list parameters. This will not render as it is displayed here. All of the new line and tabs will be ignored during rendering.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Unordered Lists</title>
    </head>
    <body>
        <h1>Unordered List</h1>
        <div>

            My typical dinner shopping list:

            Milk
            Donuts
            Cookies
                Chocolate
                Sugar
                Peanut Butter
            Pepto Bismol (Could probably do without if dinner wasn't all cookies)
            
        </div>
    </body>
</html>
```

In order to correct this we can use unordered lists

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Unordered Lists</title>
    </head>
    <body>
        <h1>Unordered List</h1>
        <div>

            My typical dinner shopping list:
            <ul>
                <li>Milk</li>
                <li>Donuts</li>
                <li>Cookies
                    <ul>
                        <li>Chocolate</li>
                        <li>Sugar</li>
                        <li>Peanut Butter</li>
                    </ul>
                </li>
                <li>Pepto Bismol</li>
            </ul> 
        </div>
    </body>
</html>
```

This will force the expected rendering and will even assign bullet points to each list item.

### **Ordered Lists**

The syntax for ordered lists is identical to un-ordered lists. You simply make the following replacement

```html
    <ul> becomes <ol>
    and </ul> becomes </ol>
```

These changes will switch the "Unordered" bullet points into Ordered numbers.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Ordered Lists</title>
    </head>
    <body>
        <h1>Ordered List</h1>
        <div>
            Oreo Cookie Eating Procedure:
            <ol>
                <li>Open Box</li>
                <li>Remove 3 cookies</li>
                <li>Make a double oreo
                    <ol>
                        <li>Remove the top from 2 cookies</li>
                        <li>Place the third un-split cookie on the cream of an opened cookie</li>
                        <li>Place the second opened cookies cream on the outside of the cookie that was inserted</li>
                    </ol>
                </li>
                <li>Enjoy</li>
            </ol> 
        </div>
    </body>
</html>
```

## **Character Entity**

HTML uses certain characters for syntax. In order to use certain characters for content.

```html
< = &lt;
> = &gt;
& = &amp;
```

This is useful in cases where we want to use these characters inside deisplayed text.

```html
<p>Don't be afraid to be &lt; then 100% success &amp; &gt; more:</p>
```

Which will display properly.
If you try to use the symbold you will see syntax highlighting that will indicate why text is missing

```html
<p>Don't be afraid to be <then 100% success & > more:</p>
```

While it may more closely resemble what is rendered on the webpage HTML does not understand how to parse the chracters as plain text and instead throws out an incorrect "then" tag (Which is not a real tag).

Text inside "p" tags will automatically wrap. This can be restricted using "non-breaking" spaces. This looks like so

```html
<p>This text will wrap exactly as you would expect. This&nbsp;text&nbsp;will&nbsp;not.</p>
```

There are also instances where encoding can not properly render symbols. In Some Windows encoding "utf-8" double-quotes may not be rendered properly. If you use the "&;" syntax to declare them trhen the browser or application should be able to render those characters

```html
<p>"This may cause errors"</p>
<p>&quot;This is less likely too&quot;</p>
```

## **Links**

Using links in HTML is important it allows you to reference other pages on your website and pages outside of your webpage.

Links are specified with an "a" element with an "href" tag.

You can specify relative as well as full path url links.
The title element is what will be displayed when hovering the link.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Internal Links</title>
    </head>
    <body>
        <h1>Internal Links</h1>
        <section>
            We can create links to files in the same directory as this html file using the following syntax:
            <a href="same-directory.html" title="Same directory link">
                Linking to a file in the same directory
            </a>
            <a href="same-directory.html" title="Same directory div link">
                <div>
                    Div linking to a file in the same directory
                </div>
            </a> 
        </section>
    </body>
</html>
```

The fact that you can wrap the "a" tag around block elements allows you to make entire files and images into links. This makes it easy to write and allows the end-user to have the expected experience.

You can also use the "target" element to allow links to open in a new tab.

```html
<a href="link.html" target="_blank">This link will open in a new tab</a>
```

You can also use "a href" to link to different parts of the same page:

```html
<a href="#section1">Section 1</a>

<section id="section1">
    A click on the link above will move the browser to this segment of the page.
</section>
```

These links will work to jump to any item that can receive the "id" tag parameter.

## **Images**

```html
<p>
    <img src="source-of-image.png">Text to follow will be displayed on the same line as the bottom of the photo and continue until page width is depleted. The remaining text will be displayed underneath the image and continue in a normal paragraph format
</p>
```

If you specify width and height the layout will be interpreted from these attributes even if the image does not load in correctly or in time.

## **Comments**

```html
<!-- 
    Anything included in between this exact opening and closing bracket will be ignored.
    Any number of spaces, tabs, new lines, and even html tagging can be used in between.
    As long as they are closed properly.  
-->
```