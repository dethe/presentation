## The Web as a Medium of Expression

### Amber Frid-Jimenez and Dethe Elza

#### DESN 312 F001S: 2D Design Concentration



## What is the Web?

The web is a collection of *documents* interconnected by *links*. In this course we will explore the nature of these documents and links as tools for expressing design.



# Documents


A document is a bunch of text with some special constraints applied. Each of these sets of constraints we will call a language. Web documents are built using several interlocking languages which perform different roles in the design process: HTML (Hypertext Markup Language), CSS (Cascading Style Sheets), and JavaScript.



# HTML


HTML defines the structure and content of a document. It consists of a combination of *tags* and text. Some tags may be nested to express more complex structure. Most of you have probably seen an HTML tag by now, it is (usually) a single word or letter surrounded by less-than and greater-than signs, also called "angle brackets".

Examples of tags are `<a>`, `<div>`, `<blockquote>`, etc. The HTML5 spec defines over 100 different tags, but we will focus on how to use a subset of these.


HTML documents are what is called "mixed-content" which means that tags can contain both tags and regular text, although some tags have restrictions on what they can contain.

Some tags have closing tags, which start with a less-than and a slash character (`</`) rather than just a less-than, to indicate where the tag ends. Other tags are self-closing and have no-end tag.


Tags can also have *attributes* which give further information to a tag. An attribute is a name followed by an equals sign, followed by a quoted value, all within the opening tag and separated from the tag name (and other attributes) by one or more spaces. Examples of tags with attributes are `<a href="http://example.com/">For example</a>`, `<img src="image.jpg">` and `<div id="main" class="content block">main content goes here</div>`.



#CSS


Style sheets give us the ability to change what a web page looks like, without changing the structure of the HTML on the page. Sites like http://csszengarden.com/ demonstrate just how far this concept can be taken. And while CSS can change what font is used, and what colours, it can be used for much more than that too, including where on the page something is displayed or whether it is shown at all, display changes when a tag is selected, hovered, or otherwise interacted with, control animations, apply effects like shadows and gradients, etc.



# JavaScript

## Enough programming to be dangerous


There are two main types of programming in web pages. The first is like any other programming language: you can define data structures, build loops and conditions, respond to events. But because JavaScript is (traditionally) embedded in a web page, you also have access to that page in a structured way. The document of the page is exposed to JavaScript using a set of conventions called the Document Object Model (DOM), which gives access to the HTML of the page, but also the styles (CSS) and even the scripts (JavaScript).


Many of the HTML tag that interest us in this course: `<canvas>`, `<img>`, `<audio>`, `<video>`, `<svg>` will be accessed from JavaScript to provide interation, customization, and playfulness. In fact, the only purpose of the `<canvas>` tag is to give us a place to draw in with JavaScript.


Between all of these tools, we have a lot of options and have to make decisions about trade-offs. Let's start with a simple example: three ways to draw a blue square.


First: HTML and CSS only

<iframe width="100%" height="300" src="http://jsfiddle.net/dethe/2jZgb/embedded/result,html,css" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

One element, three style rules. Easy!


Second: SVG

<iframe width="100%" height="300" src="http://jsfiddle.net/dethe/5TZcn/1/embedded/result,html" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Two elements, nothing else. The `svg` element is only there to create a drawable area for the `rect` element to draw into.


Third: Canvas

<iframe width="100%" height="300" src="http://jsfiddle.net/dethe/JvVrs/embedded/result,html,js" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Like the `svg` tag, the `canvas` tag is only there to define an area to draw into, but this time we draw using Javascript rather than tags. And there is more setup to do, getting a context. Why would we go to more effort for the same result?
