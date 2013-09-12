# The Web as a Medium of Expression

### Amber Frid-Jimenez and Dethe Elza

#### DESN 312 F001S: 2D Design Concentration



# Week 2: CSS


Last week we took a whirlwind tour of HTML, CSS, Javascript, with a little bit of SVG, to give an idea of all the moving parts.

And we got to play around with the `<div>` element and some basic CSS for positioning, sizing, and changing colours.

Today, we're going to look at more CSS (we will come back to HTML and explore other tags later).



# Units

One of the keys to understanding CSS is to understand units. Nearly every number in CSS is expressed along with the units it is measured in. Last week we kept ourselves to pixels units (`px`), but there are many options and they all have their uses.


### Units in CSS

The first thing to understand about units is that they are used for lengths of things in CSS.

The second thing to understand is that they aren't what they sound like. Units like `px`, `in`, and `cm` look like they would represent pixels, inches, and centimeters, but they don't not exactly. Because the number of pixels varies with the device, and the distance a device is from the viewer's eyes also varies, these "absolute" units are defined to be *roughly* an inch or centimeter, and pixels are 96 per *rough inch*.


So there are 96 `px` per `in` and other absolute lengths obey the same relationships in CSS that they do in real life: 10 `mm` per `cm`, 2.54 `cm` per `in`. There are two leftovers from typesetting: points and picas. There are 72 `pt` per `in` and 12 `pt` per `pc`.


But absolute measurements are not the only game in town. Relative measurements abound. Four are relative to the font in use: `em` is the calculated `font-size` of the the element, `ex` is the height of the lowercase letter "x" in the current font, `ch` is the width of the character "0" (zero) in the current font, and `rem` is the `font-size` of the *root element* (not the current element), which is handy because it doesn't change depending on which element is selected.


There are also measurements which are relative to the viewport, the visible portion of the document. A `vh` is 1/100th of the height of the viewport and `vw` is 1/100th of the width of the viewport. A `vmin` is 1/100th of either the width or height, whichever is less, and `vmax` is the same but for whichever is larger.


Not all of these are supported in every browser, although support is good across the "Evergreen" browsers like Firefox and Chrome.


Lengths can also be specified as a percent of the nearest sized parent element. So a `<div>` with a `width: 40%;` which is nested within a `<div>` that has `width: 100px` would end up being 40 `px` wide.


CSS units always join the numeric measure with the name of the unit being measured in, which can be a gotcha for newcomers to CSS.

Always `19em`. Never `19 em`.

Always `45%`. Never `45 %`.

Always `600px`. Never 600 px`.


### For more info

* https://developer.mozilla.org/en-US/docs/Web/CSS/length
* https://hacks.mozilla.org/2013/09/css-length-explained/



# Colors

Colors are another confusing area in CSS, because there are many ways to express them. There are also multiple parts of an element that can have color applied. So far, we've used `background-color` to change the color of `<div>`s, but you can also use `color` for foreground color (mostly for text), `border-color` for borders, even `border-left-color` to only change the color of the left border (you can do this for top, right, and bottom borders as well).


So given all of that to color, we have a lot of ways to actually tell the browser what color(s) to use. 

* Keywords: `black`, `white`, `green`, `blue`, `slategrey` (`slategray` too!)
* Special keywords: `transparent`, `currentColor`
* Hexadecimal notation for RGB: `#000000` (black) to `#FFFFFF` (white) with `#FF0000` being full red, `#00FF00` being full green, and `#0000FF` being full blue. Capitalization does not matter, `#F1F2F3` is the same as `#f1f2f3`.
* Hexadecimal shorthand: repeated characters in each pair can be skipped to give a 3-hex version (and *only* 3): `#FA0` is the same as `#FFAA00`.


* rgb(integer, integer, integer): where integer goes from 0 to 255 (255 is the decimal version of hexadecimal FF)
* rgb(percent, percent, percent): where percent goes from 0% to 100%
* hsl(hue, saturation, lightness): where hue is degrees around the color wheel (ROYGBIV: red is 0, green is 120, blue is 240), saturation and lightness are both expressed as percents.
* rgba(integer, integer, integer, float): the rgb portion is written the same as for rgb (3 integers up to 255 *or* 3 percents), but the alpha is (confusingly) a floating-point (decimal) number between 0 and 1. Alpha of 0 is fully transparent, alpha of 1 is fully opaque.
* hsla(): hsl plus alpha


### Some helpful tools

* [Lexadecimal](http://lexadecimal.com/) fun with hexadecimal "names"
* [HSL Picker](http://mothereffinghsl.com/)
* [Color Values](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) includes valid color names
* [Coding Colors Easily Using CSS3 hsl() Notation](http://www.useragentman.com/blog/2010/08/28/coding-colors-easily-using-css3-hsl-notation/)
* [Color converter](http://serennu.com/colour/hsltorgb.php) HSL->RGB->Hex
* [Adobe Kuler](https://kuler.adobe.com/create/color-wheel/) Color picker



# Positioning

We've already explored positioning, but there is more that we can do.

* Nesting
* Absolute / Relative / Fixed / Etc.
* Responsive Design (mobile-first)
* Tables: Evil or Just Wrong
* Grid systems
* Flexboxes: the new hotness
* And yes, there is more.


### Nesting

When one positioned `<div>` is nested inside another, it takes it's position from the upper-left of the outer element, rather than of the document or window. This can be exploited for various effects, especially when we realize that `position:absolute` can be used not just for `top` and `left` as we've done up until now, but also for `bottom` and `right`.


### Using different units

Positioning using relative units, such as `em` or `vmin` can be helpful.

### Using non-absolute positioning

Using `position: absolute` is really relative to the parent element with positioning. We can also use `position: relative` which is relative to the flow of the document (layout is based on non-absolutely-positioned elements which have come before it).

Other options include `static` (the default), `fixed` (don't move when the user scrolls), and `inherit` (use parent's position).



# Sizing

Again, we've covered sizing somewhat, but should explore in more depth.

* Setting width vs. setting height
* Natural sizes
* Padding, Margin, Borders, Outlines



# Fonts and Text

This is a big (BIG) topic and we're not going to go over every possible aspect of it. What we will do is go over adding custom fonts, why you need a fallback for those, what some of the common CSS rules are for text and fonts, and as a bonus: how to use icon fonts.


### Custom Fonts

The easiest way to add a custom font is to use Google Fonts, find the font you'd like, click the Quick-use button, and follow the instructions to embed the font in your web document and use it in your CSS rules.

There are other tools, like Font Squirrel, but it's hard to beat this for simplicity.


### Styling text and fonts

* `color`: text color
* `text-transform`: none, capitalize, uppercase, lowercase, or full-width
* `text-align`: left, right, center, justify, start, end, match-parent, ...
* `font-family`: a list of fonts to try, in order of preference
* `font-size`: how big the font should be, measured in any unit
* `font-style`: normal, italic, oblique, inherit
* `font-weight`: normal, bold, lighter, bolder, inherit, ...


### Icon Fonts

Icon fonts can give you a rich set of graphics to use in your page that are scalable and stylable, without having to manage a bunch of .png files or the downloads they entail.

* [IcoMoon](http://icomoon.io/app/#library) Select and customize icon fonts
* [We Love Icon Fonts](http://weloveiconfonts.com/) Like Google Fonts, but for icon fonts

Using icon fonts is generally a matter of adding them as generated content to selected elements, which takes us to our next topic.



# Generated Content

CSS has several ways to add new content to the page. You can have rules to add content before and/or after a matching tag. You can specify bullets and numbering styles for outlines. And you can add many interesting effects using borders, shadows, and background patterns.


### Inserting content from CSS

The ::before and ::after selectors can specify content which will be inserted into the document before or after the selected element, and can provide other styling to that content. This can be used to add a specific character from an icon font, for instance.

```
div::before{
	content: '';
	position: absolute;
	background-color: blue;
	left: -50px;
	top: 0;
	width: 50px;
	height: 50px;
}
```

The content part is mandatory and can be any text, everything else is optional.


### Borders, shadows, backgrounds

Some of the options here are best show by example:

* [Text Shadows](http://mothereffingtextshadow.com/) Click "all the way"
* [Box Shadows](http://css3gen.com/box-shadow/)
* [Border Radius](http://css3gen.com/border-radius/)
* [Gradients](http://www.colorzilla.com/gradient-editor/)
* [Patterns](http://lea.verou.me/css3patterns/)



# Transforms

* [Animatable](http://leaverou.github.io/animatable/)
* [Transform Generator](http://www.westciv.com/tools/transforms/)



# More Inspiration

* [Polygons](http://kizu.ru/Polygons/)
* [Beehive](http://dethe.github.io/beehive/)
* [CSS1K](http://css1k.com/)
* [Goodnight Moon](http://css1k.com/#goodnight_moon)
* [CodePen](http://codepen.io/popular/)
* [Pure CSS At-At](http://www.anthonycalzadilla.com/css3-ATAT/)


