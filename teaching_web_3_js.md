# The Web as a Medium of Expression

### Amber Frid-Jimenez and Dethe Elza

#### DESN 312 F001S: 2D Design Concentration



# Week 3: JavaScript


So far we have have 10,000 meter overviews of HTML and CSS. This week we're going to start looking at giving our sites behaviour over time and interactivity with users using JavaScript.

We're going to introduce two main concepts: the Document Object Model and events. Next week we will dive into Javascript in more depth



## Document Object Model (DOM)

The DOM is what we call HTML (and CSS) when we access it from JavaScript. It allows us to create, add and remove tags (which are called elements in the DOM and I tend to use the two words interchangably), change attributes, and change styles.


## Adding new elements

Adding an element is a two-step process. First we need to create the element, then we need to add it to the document. We may also need to find the parent element we want to add it to (unless we're adding to the `<body>` element, which is always available). For example:

```javascript
var newDiv = document.createElement('div');
document.body.appendChild(newDiv);
```


## Removing elements

Again, you will need to access the parent element that you are removing from, as well as the element you are removing. Fortunately, elements already know their parents. We'll remove an element that has the class "green" (if there is more than one element with class "green" it will only remove the first one) by finding the element using the `querySelector` method, which uses the same selectors we've already been using in CSS.

```javascript
// A comment in Javascript starts with two slashes and
// continues to the end of the line

// The class selector starts with a "." just like in CSS
var elementToRemove = document.querySelector('.green');
elementToRemove.parentElement.removeChild(elementToRemove);
```



## Changing attributes

We can get, add, change, and remove attributes. Adding and changing are really the same thing, the only difference is whether the element already had value for that attribute.

```javascript
var newLink = document.createElement('a'); // Create a new anchor tag
// An anchor tag isn't much good without linking *to* something
newLink.setAttribute('href', 'http://js1k.com/2013-spring/demo/1507');
// And it has to have content so we have something to click on
newLink.textContent = 'Pointillism';
// An element has to be part of the document somewhere or it won't be seen
document.body.appendChild(newLink);
```


## Getting and removing attributes

Sometimes we just want to know what the value of an attribute it, and sometimes we want to get rid of the attribute altogether.

```javascript
var element = document.querySelector('.importantForm');
// We're going to assume for the sake of this that an element with class "importantForm" exists
var formaction = element.getAttribute('action');
// make sure the form is enabled
element.removeAttribute('disabled');
```


## Changing styles

For changing styles on specific elements, we could just change the `style` attribute, which would work just like if we set the attribute when we wrote the HTML code. But using JavaScript and the DOM we can also set individual style values to get much more fine-grained control.

```javascript
var img = document.querySelector('#movingImage'); // we can use any CSS selector
// An element's style property is the gateway to all of its style values
img.style.display 'absolute';
img.style.top = '100px'; // remember to use units
img.style.left = '12%'; // Any CSS units will do
```



# Events

JavaScript in the browser is different from most programming languages because it comes with a rich context by being embedded in a page in a browser. So along with all the things you would normally find in a programming language (variables, loops, conditionals which we will cover in greater detail next week), you also have events coming from the browser when certain things happen.

Common events of interest can be mouse clicks, mouse movement, and keypresses. There are many more, but that's enough to get the idea. There is also a background event loop which we can interact with for things that reoccur over time. Timing isn't an event in Javascript, but is similar in how we can respond to it.


## Mouse clicks

<a class="jsbin-embed" href="http://jsbin.com/iGIDAge/1/embed?output,js,html,css">JS Bin</a><script src="http://static.jsbin.com/js/embed.js"></script>

For the CSS I am using nth-child selectors which you can learn more about here: http://nthmaster.com/

## Mouse movement

What can you find in this example that is new to you?

<a class="jsbin-embed" href="http://jsbin.com/AmiLeVE/3/embed?output,js,html,css">JS Bin</a><script src="http://static.jsbin.com/js/embed.js"></script>

## Keypresses

<a class="jsbin-embed" href="http://jsbin.com/EcEyUBU/4/embed?html,js,output">JS Bin</a><script src="http://static.jsbin.com/js/embed.js"></script>

Ask me about `switch` statements.

## Timing



# A little HTML, Some CSS

For this week's exercise we're going to let you use images that you create using whatever software you like (even your camera). In order to get your images into the web page, you will need to put them on the web somewhere (doesn't matter where, could be Flickr, Facebook, Photobucket, or elsewhere, as long as you have a URL to your image). Then we'll need a way to include your image into the web page. We'll a couple of techniques for this: the `<img>` tag and the `background-image` style.


## The `<img>` tag


## The `background-image` style


## Making "sprites"


# More Inspiration



