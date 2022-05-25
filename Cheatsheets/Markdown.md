# ***Markdown***

* [Basics](#basics)
* [Latex](#latex)

## **Basics**

* [Headers](#headers)
* [Formatting](#formatting)
* [Style](#style)
* [Lists](#lists)
* [Code Blocks](#code-blocks)
* [Math Functions](#math-functions)
* [Links](#links)

### **Headers**

```markdown
The main header should be defined with #

# Header

Chapters should be defined with ##

## Chapter 1

## Chapter 2

And you add a # for each level of nesting on sub-headers.

# Title

## Chapter 1

### Subsection 1

### Subsection 2

## Chapter 2

### Subsection 1

### Subsection 2
```

It would be a better practice to give each header and sub-header a uniquely identifiable name. The listing above is simply to show how the nesting works. But there are many tools that allow for quickly searching documents and making table of contents by headers so practical naming conventions and organization styles make your document more accessible to tools that others may already be using.

### **Formatting**

If you want to add a space between paragraphs or sentences then two new lines are needed.
Sentences can be written on new-lines and will automatically wrap if only one new line is introduced.
This comes down to personal preference really but it is a style choice I make do to line wrapping in my editor.

Two lines of space creates a new paragraph.
There should also be an empty new line between any header elements or code segments.
Lines should not having trailing spaces and there should be a single new line at the end of the document.
If you continue a line on the next line the editor will treat it as a space.
In case there is any wrapping done by the viewer.

Looking at these paragraphs raw vs how they are rendered should provide a good sense of how the documents are displayed in editor and in a rendered view.

```markdown
If you want to add a space between paragraphs or sentences then two new lines are needed.
Sentences can be written on new-lines and will automatically wrap if only one new line is introduced.
This comes down to personal preference really but it is a style choice I make do to line wrapping in my editor.

Two lines of space creates a new paragraph.
There should also be an empty new line between any header elements or code segments.
Lines should not having trailing spaces and there should be a single new line at the end of the document.
If you continue a line on the next line the editor will treat it as a space.
In case there is any wrapping done by the viewer.

Looking at these paragraphs raw vs how they are rendered should provide a good sense of how the documents are displayed in editor and in a rendered view.
```

### **Style**

It is very easy to bold or italicize text in Markdown.

* "**"  Should wrap text meant to be bold.
* "*"   Should wrap text meant to be italic.
* "***" Should wrap text meant to be bold and italic.

```markdown
**Bold Text**
*Italic Text*
***Both Text***
```

**Bold Text**
*Italic Text*
***Both Text***

As a personal preference I bold sub headers and Bold and Italicize the main header.

### **Lists**

You can define ordered and un-ordered lists.

#### *Un-Ordered Lists*

You have already seen "Un-ordered" lists in my chapter links.
Using an asterix at the start of a new-line will create bulleted entry.
You need to end each line (Remember it is best practice to avoid trailing spaces) before creating a new entry.
So each entry appears on it's own line.
Despite the name Un-ordered lists still appear in the order they are written in.
The main point is that the order of the items isn't usually relevant when using bulleted lists.
Such as a grocery list

```markdown
* Potatoes
* Ham
* Shredded Cheese
* Milk
* Dove Chocolate Bar
* Soap
```

* Potatoes
* Ham
* Shredded Cheese
* Milk
* Dove Chocolate Bar
* Soap

#### *Ordered Lists*

Ordered lists are the same as unordered list except you provide a number followed by a period and space.

```markdown
1. Type the next sequential number.
2. Type a period and Space.
3. Provided the text for the item.
4. Start a new-line (No trailing spaces).
5. Repeat 1-4 for each individual item until the task is complete.
```

1. Type the next sequential number.
2. Type a period and Space.
3. Provided the text for the item.
4. Start a new-line (No trailing spaces).
5. Repeat 1-4 for each individual item until the task is complete.

#### *Nesting*

Lists types can be combined and nested.
Nested items should be organized by a single tab per nesting level.

```markdown
1. Check TODO List
    * Groceries
        * Potatoes
        * Ham
        * Shredded Cheese
        * Milk
        * Dove Chocolate Bar
        * Soap
    * Work
    * Sleep
2. Organize day around TODO list
```

1. Check TODO List
    * Groceries
        * Potatoes
        * Ham
        * Shredded Cheese
        * Milk
        * Dove Chocolate Bar
        * Soap
    * Work
    * Sleep
2. Organize day around TODO list

### **Code Blocks**

Code blocks (The inset portions of code you have seen above already) can be defined rather easily.
All you need to do is specify the language and place the code between two sets of triple back-ticks "```".

````markdown
```python
import numpy as np

x = np.array([1, 2, 3, 4])
```
````

In the case above in order to display the code block within the code block it is wrapped in "````" instead of "```" as pictured.
The above code block is displayed as:

```python
import numpy as np

x = np.array([1, 2, 3, 4])
```

### **Math Functions**

Functions can be defined in-line with $x = y$ and are written as follows.

```markdown
$x=y$
```

Or they can be separated and space formatted in the center of the document as so
$$ x = y $$

```markdown
$$x=y$$
```

### **Links**

Links are fairly simple in Markdown.
You name the link inside square brackets and immediately provide the source in parenthesis.

```markdown
[Name of Link](www.example.com)
```

This will link to www.example.com and appears rendered as so.

[Name of Link](www.example.com)

Links behave like any other line of text.
If a single new-line is used then they will wrap to the next available space.
[Name of Link](www.example.com)

You can also link to different portions of the document.
You must provide the name of the link as before.
For interanl header linking you must specify the header name following a "#".
All letters should be lower-cased and spaces replaced with "-"
This is what the links code for the Basics Section looks like:

```markdown
* [Headers](#headers)
* [Formatting](#formatting)
* [Code Blocks](#code-blocks)
* [Math Functions](#math-functions)
* [Links](#links)
```

You can link to relative pages as well and even mark specific headers.

[Main Repository README](../README.md)

[Conflict Resolution CSS](../Coursera/Frontend/CSS/README.md#conflict-resolution)

Another wonderful aspect is that links only look for the text and ignore styling components.
This is another benefit of using unique names across chapters and segments.

## **Latex**

* Formatting Fractions

$$\frac{(x+1)}{1}$$

```latex
$$\frac{(x+1)}{1}$$
```
