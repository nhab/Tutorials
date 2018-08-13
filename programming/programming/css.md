Describes how HTML elements are to be displayed
## Terms and concepts
### padding
distance between borders  and <b>neighbouring</b> objects.

### margin
distance between borders and <b>internal</b> objects.
### selectors

#### The element Selector
:selects HTML elements based on the element name.
:X
```css
p {
	text-align: center;
	color: red;
}

or 
tr:hover{background-color: #f5f5f5}	 
```
### The id Selector
:uses the id attribute of an HTML element to select a specific element.
:X
```html
<!DOCTYPE html>
<html>
<head>
<style>
#para1 {
	text-align: center;
	color: red;
}
</style>
</head>
<body>

<p id="para1">Hello World!</p>
<p>This paragraph is not affected by the style.</p>

</body>
</html>
```
### The class Selector
: selects elements with a specific class attribute.
:X
```css
<!DOCTYPE html>
<html>
<head>
<style>
.center {
	text-align: center;
	color: red;
}
</style>
</head>
<body>

<h1 class="center">Red and center-aligned heading</h1>
<p class="center">Red and center-aligned paragraph.</p> 

</body>
</html>
```
#### other selectors

| syntax            |    Example            | Description
|----|----|----
|element element 	|	div p 				|	Selects all ```<p>``` elements inside ```<div>``` elements 	
|element>element 	|	div > p 			|	Selects all ```<p>``` elements where the parent is a ```<div>``` element 	
|element+element 	|	div + p 			|	Selects all ```<p>``` elements that are placed immediately after ```<div>``` elements 	
|element1~element2 	|	p ~ ul 				|	Selects every ```<ul>``` element that are preceded by a ```<p>``` element 	
|[attribute] 		|	[target] 			|	Selects all elements with a target attribute 	
|[attribute=value] 	|	[target=_blank] 	|	Selects all elements with target="_blank" 	
|[attribute~=value] |		[title~=flower] |		Selects all elements with a title attribute containing the word "flower" 	
|[attribute\|=value] |		[lang\|=en]		|		Selects all elements with a lang attribute value starting with "en" 	
|[attribute^=value] |		a[href^="https"] |		Selects every ```<a>``` element whose href attribute value begins with "https" 	
|[attribute$=value] |		a[href$=".pdf"]   |		Selects every ```<a>``` element whose href attribute value ends with ".pdf" 	
|[attribute*=value] |		a[href*="w3schools"] | 	Selects every ```<a>``` element whose href attribute value contains the substring "w3schools" 	
|:active 			|	a:active 		|		Selects the active link 	
|::after 			|	p::after 		|		Insert something after the content of each ```<p```> element 
|::before 			|	p::before 		|		Insert something before the content of each ```<p>``` element 	
|:checked 			|	input:checked 	|		Selects every checked ```<input>``` element 	
|:disabled	 		|	input:disabled 	|		Selects every disabled ```<input>``` element 	
|:empty 			|		p:empty 	|			Selects every ```<p>``` element that has no children (including text nodes) 	
|:enabled 			|	input:enabled 	|		Selects every enabled ```<input>``` element 	
|:first-child	 	|	p:first-child 	|		Selects every ```<p>``` element that is the first child of its parent 	
|::first-letter	 	|	p::first-letter |		Selects the first letter of every ```<p>``` element 	
|::first-line 		|	p::first-line 	|		Selects the first line of every ```<p>``` element 	
|:first-of-type 		|	p:first-of-type |		Selects every ```<p>``` element that is the first ```<p>``` element of its parent 	
|:focus 				|	input:focus 	|		Selects the input element which has focus 	
|:hover 				|	a:hover 		|		Selects links on mouse over 	
|:in-range 			|	input:in-range 	|		Selects input elements with a value within a specified range 	
|:invalid 			|	input:invalid 	|		Selects all input elements with an invalid value 	
|:lang(language) 	|	p:lang(it) 		|		Selects every ```<p>``` element with a lang attribute equal to "it" (Italian) 	
|:last-child 		|	p:last-child 	|		Selects every ```<p>``` element that is the last child of its parent 	
|:last-of-type 		|	p:last-of-type 	|		Selects every ```<p>``` element that is the last ```<p>``` element of its parent 	
|:link 				|	a:link 			|		Selects all unvisited links 	
|:not(selector) 		|	:not(p) 		|		Selects every element that is not a ```<p>``` element 	
|:nth-child(n) 		|	p:nth-child(2) 	|		Selects every ```<p>``` element that is the second child of its parent 	
|:nth-last-child(n) 	|	p:nth-last-child(2)| 	Selects every ```<p>``` element that is the second child of its parent, counting from the last child 	
|:nth-last-of-type(n) |	p:nth-last-of-type(2)| 	Selects every ```<p>``` element that is the second ```<p>``` element of its parent, counting from the last child 	
|:nth-of-type(n) 	|	p:nth-of-type(2) 	|	Selects every ```<p>``` element that is the second ```<p>``` element of its parent 	
|:only-of-type 		|	p:only-of-type 		|	Selects every ```<p>``` element that is the only ```<p>``` element of its parent 	
|:only-child 		|	p:only-child 		|	Selects every ```<p>``` element that is the only child of its parent 	
|:optional 			|	input:optional 		|	Selects input elements with no "required" attribute 
|:out-of-range 		|	input:out-of-range 	|	Selects input elements with a value outside a specified range 	
|:read-only			| 	input:read-only 	|	Selects input elements with the "readonly" attribute specified 	
|:read-write 		|	input:read-write 	|	Selects input elements with the "readonly" attribute NOT specified 	
|:required 			|	input:required 		|	Selects input elements with the "required" attribute specified 	
|:root 				|	:root 				|	Selects the root element of thedocument 	
|::selection 		|	::selection 		|	Selects the portion of an element that is selected by a user 	 
|:target 			|	#news:target 		|	Selects the current active #news element (clicked on a URL containing that anchor name) 	
|:valid 			|	input:valid 		|	Selects all input elements with a valid value 	
|:visited 			|	a:visited 			|	Selects all visited links 	
	
### Comments
starts with /* and ends with */
### rule-set
:consists of a <b>selector</b> and a declaration block(a set of prperty:value):
```css
h1      { color      : blue  ;   font-size : 12px;  }
```
### combinator 
Explains the relationship between the selectors.
```css
/*The following example selects all <p> elements inside <div> elements:*/ 
div p {
    background-color: yellow;
}
```
### Pseudo-classes

define a special state of an element<br>
(for example on  mouse  over it or when got focus or  visited links)

<br>syntax
```css
selector:pseudo-class {
	property:value;
}
```
Example:
```css
/* unvisited link */
a:link {
    color: #FF0000;
}

/* visited link */
a:visited {
    color: #00FF00;
}

/* mouse over link */
a:hover {
    color: #FF00FF;
}
```
### pseudo-element
to style specified parts of an element.
Syntax (double colon)
```css
selector::pseudo-element {
	property:value;
}
```
Example
```css
	p.intro::first-letter {
		color: #ff0000;
		font-size:200%;
	}
```
:{
```css
::first-line
::first-letter
::before 
::after
::selection 
:matches the portion of an element that is selected by a user.
:X ::selection {   color: red;  background: yellow;}
```
### Image Sprites
```
:An image sprite is a collection of images put into a single image.
A web page with many images can take a long time to load and generates multiple server requests.
Using image sprites will reduce the number of server requests and save bandwidth.
```
### Counters

counters are like "variables":

Are variables whose values may be incremented by ```counter-increment```  property<br>
to track how many times they are used.<br>
This lets you adjust the appearance of content<br> 
based on its placement in the document.<br>

To work with CSS counters we will use the following properties:<br>

|function|description|
|----|----|
|counter-reset | Creates or resets a counter|
|counter-increment | Increments a counter value|
|content 		| Inserts generated content|
|counter() or counters() | Adds the value of a counter to an element|

Example:
```html
<html>
<style>
	body {
		counter-reset: section;                    /* Set the section counter to 0 */
	}

	h3::before {
	counter-increment: section;                /* Increment the section counter*/
	content: "Section " counter(section) ": "; /* Display the counter */
	}
</style>
<body>
	<h3>Introduction</h3>
	<h3>Body</h3>
	<h3>Conclusion</h3>
</body>
</html>
```
### CSS Functions
```css
attr() 							Returns the value of an attribute of the selected element
	/* Simple usage */
	attr(data-count);
	attr(title);

	/* With type */
	attr(src url);
	attr(data-count number);
	attr(data-width px);

	/* With fallback */
	attr(data-count number, 0);
	attr(src url, '');
	attr(data-width px, inherit);
	attr(data-something, 'default'); 	
calc()				 			Allows you to perform calculations to determine CSS property values 	
linear-gradient()	 			Creates an "image" which represents a linear gradient of colors 	
radial-gradient() 				Creates an "image" which represents a gradient of colors radiating from
								the center of the gradient 	
repeating-linear-gradient() 	Creates an "image" consisting of repeating gradients 	
repeating-radial-gradient() 	Similarly to radial-gradient(), but it automatically repeats the color stops infinitely
								in both directions
```

### opacity / Transparency

	:to add transparency to the background of an element, all of its child elements become transparent as well
	can take a value from 0.0 - 1.0. 
```css
filter:alpha(opacity=x). /*The x can take a value from 0 - 100.*/
```
### border/outline/devider
```css
border-style
	dotted - Defines a dotted border
	dashed - Defines a dashed border
	solid - Defines a solid border
	double - Defines a double border
	groove - Defines a 3D grooved border. The effect depends on the border-color value
	ridge - Defines a 3D ridged border. The effect depends on the border-color value
	inset - Defines a 3D inset border. The effect depends on the border-color value
	outset - Defines a 3D outset border. The effect depends on the border-color value
	none - Defines no border
	hidden - Defines a hidden border
border-width: 5px;
border-color: green;
border-collapse: collapse;
border-radius 
	:you can give any element "rounded corners"
	:X
		x1
			border-radius: 25px;
		x2
			border-radius: 15px 50px 30px:
		x3:
			border-radius: 15px 90px 30px 120px;
border-image
	:you can set an image to be used as the border around an element.
	border-image property is actually a shorthand property
	:x 
		#borderimg { 
			border: 10px solid transparent;
			padding: 15px;
			-webkit-border-image: url(border.png) 30 round; /* Safari 3.1-5 */
			-o-border-image: url(border.png) 30 round; /* Opera 11-12.1 */
			border-image: url(border.png) 30 round;
		}
		</style>

border-image-source
border-image-slice
border-image-width
border-image-outset
border-image-repeat
```
```
-to temporarily set borders for all tables:
	table, td, th {	border: 1px solid black;}
-Horizontal Dividers
	th, td {    border-bottom: 1px solid #ddd;}
```
## outline
:is a line that is drawn around elements (outside the borders) to make the element "stand out".
	However, the outline property is different from the border property 
	- The outline is NOT a part of dimensions of an element ; 
	total width and height of the element is not affected by the width of the outline.
```css
outline-style: solid;//dotted;dashed;double;groove;ridge;inset;outset;
outline-color: red;
outline-width: thick;
```
### outline-offset
adds space between an outline and the edge or border of an element.
Example
```css	
div {
	border: 1px solid black;
	outline: 1px solid red;
	outline-offset: 15px;
}
```
### Positions /layout
```css
		right  : 0px;/*the distance of the element from right is 0px*/
		left   : 0px;/*the distance of the element from left is 0px*/
		top    : 0px;/*the distance of the element from the top is 0px*/
		bottom : 0px;/*the distance of the element from the bottom is 0px*/
```
###	display
	- property is the most important CSS property for controlling layout
	- The display property specifies if/how an element is displayed.
	- Every HTML element has a default display value depending on what type of element it is.
	- The default display value for most elements is block or inline.
:{
#### Block-level Elements ( display: block;)
 always starts on a new line and takes up the full width available
:X 
```html
<div>
<h1> - <h6>
<p>
<form>
<header>
<footer>
<section>
```
#### Inline Elements (  display: inline;)
An inline element does not start on a new line and only takes up as much width as necessary.
:x
```html
<span>
<a>
<img>
```
#### inline-block 	
 Displays an element as an inline-level block container
. The inside of this block is formatted as block-level box, 
and the element itself is formatted as an inline-level box.
-this,acts as a floating box inside the page
Example:
```css
	.floating-box {
		display: inline-block;
		width: 150px;
		height: 75px;
		margin: 10px;
		border: 3px solid #73AD21;
	}
```
other values
| value | Description
|----|----
|flex		| 		Displays an element as an block-level flex container. New in CSS3 	
|inline-flex |		Displays an element as an inline-level flex container. New in CSS3 	
|inline-table|	 	The element is displayed as an inline-level table
|run-in 		|		Displays an element as either block or inline, depending on context
|list-item 		|	Let the element behave like a <li> element
|table 			|	Let the element behave like a <table> element 	
|table-caption 	|	Let the element behave like a <caption> element 	
|table-column-group| 	Let the element behave like a <colgroup> element 	
|table-header-group |	Let the element behave like a <thead> element 	
|table-footer-group |	Let the element behave like a <tfoot> element 	
|table-row-group| 	Let the element behave like a <tbody> element 	
|table-cell 	|		Let the element behave like a <td> element 	
|table-column 	|	Let the element behave like a <col> element 	
|table-row 		|	Let the element behave like a <tr> element
|none			 |	The element will not be displayed at all (has no effect on layout) 	
|initial 		|	Sets this property to its default value.  	
|inherit		|	 	Inherits this property from its parent element. Read about inherit

Default value: 	inline

##position
```css
			position: static; /*default;are not affected by the top, bottom, left, and right properties.
				//is not positioned in any special way;*/
			position: relative; /*is positioned relative to its normal position.*/
			position: fixed; /*it always stays in the same place even if the page is scrolled.*/
			position: absolute;/*is positioned relative to the nearest positioned ancestor */
					/*/(instead of positioned relative to the viewport, like fixed).*/
```
## z-index 
:which element should be placed in front of, or behind, the others.
:x img {position: absolute;}//makes the image be uder the content

### Margins
: to generate space around elements
:X
```css
	p {
		margin-top: 100px;
		margin-bottom: 100px;
		margin-right: 150px;
		margin-left: 80px;
	}
```
### padding 
: to generate space around content.
:X
```css
padding-top: 50px;
padding-right: 50px;
padding-bottom: 50px;
padding-left: 50px;	
```

```css
background-attachment	: fixed; /*fix positioning*/
background-position     : right top;

list-style-position: inside; /*or outside ; used to Position The List Item Markers wheter inside or outside the content*/
text-align: left; /* horizontal position of texts "INSIDE" the element (content)*/
vertical-align:bottom;/*vertical position of the content of the element*/
```
###float 
	: puts the element in the left or right of its container(parent);
	(should be used with clear property in many senarios)
Example
```css
	 float: right;/*puts the element on the right ;*/
```

### clear 
	Elements after a floating element will flow around it. To avoid this, use the clear property.

### margin: auto;
	it place the element at the center of its container.

## Dimentions /size
```css
height: 200px;
width: 50%;
max-width: 500px;
```

### flex 
specifies the length of the item, relative to the rest of the flexible items inside the same container.<br>
<b>values:</b><br>

|Value|Description
|----|----
|flex-grow 		|A number specifying how much the item will grow relative to the rest of the flexible items
|			|Example :	div:nth-of-type(1) {flex-grow: 1;}
|flex-shrink |	A number specifying how much the item will shrink relative to the rest of the flexible items
|flex-basis | The Initial length of the item. Legal values: "auto", "inherit",
|			|	or a number followed by "%", "px", "em" or any other length unit
|auto 	|		Same as 1 1 auto.
|initial |		Same as 0 1 auto. Read about initial
|none 	|		Same as 0 0 auto.
|inherit |		Inherits this property from its parent element. Read about inherit

### overflow 

specifies whether to clip content or to add scrollbars when the content of an element is too big
to fit in a specified area.<br>

values:</b><br>

|Value|Description
|----|----
|visible -| Default. The overflow is not clipped. It renders outside the box of element
|hidden  -| The overflow is clipped, and the rest of the content will be invisible
|scroll  -| The overflow is clipped, but a scrollbar is added to see the rest of the content
|auto    -| If overflow is clipped, a scrollbar should be added to see the rest of the content
|overflow-x| specifies what to do with the left/right (overflowed )edges of the content.<br> values: visibe,hidden,scroll,auto
|overflow-y| specifies what to do with the top/bottom (overflowed )edges of the content.<br> values: visibe,hidden,scroll,auto

### resize 

to prevent textareas from being resized (disable the "grabber" in the bottom right corner):
<br>Example
```css
textarea {
	width: 100%;
	height: 150px;
	padding: 12px 20px;
	box-sizing: border-box;
	border: 2px solid #ccc;
	border-radius: 4px;
	background-color: #f8f8f8;
	resize: none;
}
```

## Colors
```css
color: green;
background-color        : green;
```

### RGBA

:color values are an extension of RGB color values with an alpha channel - which specifies the opacity for a color.
	:x rgba(255, 0, 0, 0.4);

### hsl ( hue, saturation, lightness )
:HSL stands for Hue, Saturation and Lightness.
		Hue is a degree on the color wheel (from 0 to 360):
			0 (or 360) is red
			120 is green
			240 is blue
		Saturation is shining percentage value:0- 100%  .
		Lightness is also darkness percentage; 0% is dark (black) and 100% is white.
```css
hsla(hue color,shining percent, brightness perent , alpha); /*alpha value can range from 0.0 (fully transparent) to 1.0 (fully opaque).*/
```

### gradiant

#### linear gradiant

##### Top to Bottom (this is default)

background: linear-gradient(direction, color-stop1, color-stop2, ...);

:X
```css
#grad {
	background: red; /* For browsers that do not support gradients */
	background: -webkit-linear-gradient(red, yellow); /* For Safari 5.1 to 6.0 */
	background: -o-linear-gradient(red, yellow); /* For Opera 11.1 to 12.0 */
	background: -moz-linear-gradient(red, yellow); /* For Firefox 3.6 to 15 */
	background: linear-gradient(red, yellow); /* Standard syntax */
}
```

##### Left to Right

:X
```css
#grad {
	background: red; /* For browsers that do not support gradients */
	background: -webkit-linear-gradient(left, red , yellow); /* For Safari 5.1 to 6.0 */
	background: -o-linear-gradient(right, red, yellow); /* For Opera 11.1 to 12.0 */
	background: -moz-linear-gradient(right, red, yellow); /* For Firefox 3.6 to 15 */
	background: linear-gradient(to right, red , yellow); /* Standard syntax */
}
```

##### Diagonal

:You can make a gradient diagonally by specifying both the horizontal and vertical starting positions.
:X
```css
	#grad {
	background: red; /* For browsers that do not support gradients */
	background: -webkit-linear-gradient(left top, red, yellow); /* For Safari 5.1 to 6.0 */
	background: -o-linear-gradient(bottom right, red, yellow); /* For Opera 11.1 to 12.0 */
	background: -moz-linear-gradient(bottom right, red, yellow); /* For Firefox 3.6 to 15 */
	background: linear-gradient(to bottom right, red, yellow); /* Standard syntax */
	}
```

#### Using Angles

background: linear-gradient(angle, color-stop1, color-stop2); 

:X
```css
	#grad {
	background: red; /* For browsers that do not support gradients */
	background: -webkit-linear-gradient(-90deg, red, yellow); /* For Safari 5.1 to 6.0 */
	background: -o-linear-gradient(-90deg, red, yellow); /* For Opera 11.1 to 12.0 */
	background: -moz-linear-gradient(-90deg, red, yellow); /* For Firefox 3.6 to 15 */
	background: linear-gradient(-90deg, red, yellow); /* Standard syntax */
	}
```
#### MULTIPLE COLORS

```css
	#grad {
	background: red; /* For browsers that do not support gradients */
	background: -webkit-linear-gradient(red, yellow, green); /* For Safari 5.1 to 6.0 */
	background: -o-linear-gradient(red, yellow, green); /* For Opera 11.1 to 12.0 */
	background: -moz-linear-gradient(red, yellow, green); /* For Firefox 3.6 to 15 */
	background: linear-gradient(red, yellow, green); /* Standard syntax */
	}
```
#### Repeating a linear-gradient
```css
	#grad {
	background: red; /* For browsers that do not support gradients */
	/* Safari 5.1 to 6.0 */
	background: -webkit-repeating-linear-gradient(red, yellow 10%, green 20%);
	/* Opera 11.1 to 12.0 */
	background: -o-repeating-linear-gradient(red, yellow 10%, green 20%);
	/* Firefox 3.6 to 15 */
	background: -moz-repeating-linear-gradient(red, yellow 10%, green 20%);
	/* Standard syntax */
	background: repeating-linear-gradient(red, yellow 10%, green 20%);
	}
```
### Radial Gradient 
- Evenly Spaced Color Stops (this is default)
```css
	#grad {
		background: red; /* For browsers that do not support gradients */
		background: -webkit-radial-gradient(red, yellow, green); /* Safari 5.1 to 6.0 */
		background: -o-radial-gradient(red, yellow, green); /* For Opera 11.6 to 12.0 */
		background: -moz-radial-gradient(red, yellow, green); /* For Firefox 3.6 to 15 */
	
		background: radial-gradient(red, yellow, green); /* Standard syntax */
	}
```
- Differently Spaced Color Stops
```css
	#grad {
		background: red; /* For browsers that do not support gradients */
		background: -webkit-radial-gradient(red 5%, yellow 15%, green 60%); /* Safari 5.1-6.0 */
		background: -o-radial-gradient(red 5%, yellow 15%, green 60%); /* For Opera 11.6-12.0 */
		background: -moz-radial-gradient(red 5%, yellow 15%, green 60%); /* For Firefox 3.6-15 */
	
		background: radial-gradient(red 5%, yellow 15%, green 60%); /* Standard syntax */
	}
```
#### set shape
```css 
#grad {
	background: red; /* For browsers that do not support gradients */
	background: -webkit-radial-gradient(circle, red, yellow, green); /* Safari */
	background: -o-radial-gradient(circle, red, yellow, green); /* Opera 11.6 to 12.0 */
	background: -moz-radial-gradient(circle, red, yellow, green); /* Firefox 3.6 to 15 */

	background: radial-gradient(circle, red, yellow, green); /* Standard syntax */
}
```
#### Different Size Keywords
|values		|									
|closest-side |
|farthest-side|
|closest-corner|
|farthest-corner|
|background: radial-gradient(closest-side at 60% 55%, red, yellow, black);|
|background: radial-gradient(farthest-side at 60% 55%, red, yellow, black);|

### Repeating a radial-gradient
```css
	background: repeating-radial-gradient(red, yellow 10%, green 15%);
```
## shadow

### text-shadow

Example

```css
{
	color: white;
	text-shadow: 2px 2px 4px #000000;
}
```

### box-shadow

```css
box-shadow: 7px 6px grey;
box-shadow: 10px 10px 5px grey; /* blur effect */
box-shadow: 6px 7px 31px grey;/* heavy blur effect */
```

### Multiple Shadows

```css
text-shadow: 0 0 3px #FF0000, 0 0 5px #0000FF;
```

Example
```css
{
	color: white;
	text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
}
```

## Texts

### horizontal text-align
```css
text-align: center;/*left*/
text-align: justify;/* each line is stretched so that every line has equal width, and the left and right margins are straight (like in magazines and newspapers)*/
```
### decoration
```css
a {   text-decoration: none;/*  is often used to remove underlines from links*/
	/* overline ,	line-through,underline*/
}
```
### text-transform
:to specify uppercase and lowercase letters in a text.
:x    text-transform: lowercase;
### text-indent: 50px;
### Letter Spacing 
:to specify the space between the characters in a text.
:X letter-spacing: 3px; 
		:X2 letter-spacing: -3px;
### line-height
	:to specify the space between lines
	:x   line-height: 0.8;
### direction
	: to change the text direction of an element:
	:x direction: rtl;
### word-spacing 
	: to specify the space between the words in a text.
	:x 
		word-spacing: 10px;
		word-spacing: -5px;
### text-shadow 	
	:Specifies the shadow effect added to text
### text-transform 
	:Controls the capitalization of text
### unicode-bidi
	:Used together with the direction property to set or return whether the text should be overridden to
		support multiple languages in the same document
### font-family: "Times New Roman", Times, serif;
	The font-family property should hold several font names as a "fallback" system. 
	If the browser does not support the first font, it tries the next font, and so on.
	Start with the font you want, and end with a generic family, 
	to let the browser pick a similar font in the generic family, if no other fonts are available. 

### list-style-type: circle;//square  upper-roman  lower-alpha
	//List Item Markers
### list-style-image: url('sqpurple.gif'); //An Image as The List Item Marker
### text-overflow: ellipsis; /* shows ... when overflown*/
### word-wrap
	: 	Allows long words to be able to be broken and wrap onto the next line
	:x break-word;
### word-break
: property specifies line breaking rules.
	Specifies line breaking rules for non-CJK scripts
:x
```css
	p.test1 {
		word-break: keep-all;
	}

	p.test2 {
		word-break: break-all;
	}
```
### text-align-last 	Specifies how to align the last line of a text
### text-emphasis 	A shorthand for setting text-emphasis-style and text-emphasis-color in one declaration
### text-justify 	Specifies how justified text should be aligned and spaced
### text-overflow 	Specifies how overflowed content that is not displayed should be signaled to the user
### font-style: normal;//italic oblique
### font-size: 40px;
### font-size: 2.5em;
	To allow users to resize the text (in the browser menu), many developers use em instead of pixels.
	The em size unit is recommended by the W3C.
	1em is equal to the current font size. The default text size in browsers is 16px. So, the default size of 1em is 16px.
### font-size: 100%;

### font-weight: bold; //normal
### font-variant: small-caps;  //normal
```
// specifies whether or not a text should be displayed in a small-caps font
// small-caps:
// In a small-caps font, all lowercase letters are converted to uppercase letters.
// However, the converted uppercase letters appears in a smaller font size than the original uppercase letters in the text.
```
### web font
	Web fonts allow Web designers to use fonts that are not installed on the  computer of the user
	by  automatically downloading them  when needed.
#### defining a font
```css
@font-face {
	font-family: myFirstFont;
	src: url(sansation_light.woff);
}

div {
	font-family: myFirstFont;
}
```
### font descriptors
```
		Descriptor 		Values		 	Description
		font-family 	name 			Required. Defines a name for the font
		src 	URL 					Required. Defines the URL of the font file
		font-stretch 	normal
		condensed
		ultra-condensed
		extra-condensed
		semi-condensed
		expanded
		semi-expanded
		extra-expanded
		ultra-expanded 	Optional.	 	Defines how the font should be stretched. Default is "normal"
		font-style 		normal
		italic
		oblique 		Optional.	 	Defines how the font should be styled. Default is "normal"
		font-weight 	normal
		bold
		100
		200
		300
		400
		500
		600
		700
		800
		900 			Optional.		 Defines the boldness of the font. Default is "normal"
		unicode-range 	unicode-range 	Optional. Defines the range of UNICODE characters the font supports. Default is "U+0-10FFFF"
```
#### Multi-column Layout
```css
	column-count
	column-gap
	column-rule-style
	column-rule-width
	column-rule-color
	column-rule
	column-span
	column-width
```

## Images /painting
### single background 
```css
background-image        : url("paper.gif");
background-repeat		: repeat-x; //or no-repeat
```

### Multiple Backgrounds (layers)
```css
#example1 {
	background-image: url(img_flwr.gif), url(paper.gif);
	background-position: right bottom, left top;
	background-repeat: no-repeat, repeat;
}
or shorthanded
	#example1 {
		background: url(img_flwr.gif) right bottom no-repeat, url(paper.gif) left top repeat;
	}
```

### Image sizing
#### background-size
``` 
allows you to specify the size of background images
The size can be specified in
:{
	-lengths 
	-percentages 
	-keyword contain
		The contain keyword scales the background image to be as large as possible
		(but both its width and its height must fit inside the content area).
		As such, depending on the proportions of the background image and the background positioning area, 
		there may be some areas of the background which are not covered by the background image.

	-keyword cover.
		The cover keyword scales the background image so that the content area is completely 
		covered by the background image (both its width and height are equal to or exceed the content area). 
		As such, some parts of the background image may not be visible in the background positioning area.
```
#### background-origin
```css
	:specifies where the background image is positioned.
	:{values
		border-box - the background image starts from the upper left corner of the border
		padding-box - (default) the background image starts from the upper left corner of the padding edge
		content-box - the background image starts from the upper left corner of the content
			:x background-origin: content-box;
background-clip
	:specifies the painting area of the background.
	:{values
		border-box - (default) the background is painted to the outside edge of the border
		padding-box - the background is painted to the outside edge of the padding
		content-box - the background is painted within the content box
```

## Animations
### animations
			animation 
				:allows animation of most HTML elements without using JavaScript or Flash
				:?concept
					-To use CSS3 animation, you must first specify CSS styles inside the @keyframes rule
					-Keyframes hold what styles the element will have at certain times.
					To get an animation to work, you must bind the animation to an element.
				:X
```css
/* The animation code */
	@keyframes example {
		from {background-color: red;}
		to {background-color: yellow;}
	}

	/* The element to apply the animation to */
	div {
		width: 100px;
		height: 100px;
		background-color: red;

		animation-name: example;
		animation-duration: 4s;
	}
```
###animation-iteration-count
: specifies the number of times an animation should run.
animation steps are specifed by percent.
```html
<!DOCTYPE html>
<html>
<head>
<style> 
div {
	width: 100px;
	height: 100px;
	background-color: red;
	position: relative;
	-webkit-animation-name: example; /* Chrome, Safari, Opera */
	-webkit-animation-duration: 4s; /* Chrome, Safari, Opera */
	-webkit-animation-iteration-count: 3; /* Chrome, Safari, Opera */
	-webkit-animation-direction: reverse; /* Chrome, Safari, Opera */
	animation-name: example;
	animation-duration: 4s;
	animation-iteration-count: 3;
	animation-direction: reverse;    
}

/* Chrome, Safari, Opera */
@-webkit-keyframes example {
	0%   {background-color:red; left:0px; top:0px;}
	25%  {background-color:yellow; left:200px; top:0px;}
	50%  {background-color:blue; left:200px; top:200px;}
	75%  {background-color:green; left:0px; top:200px;}
	100% {background-color:red; left:0px; top:0px;}
}

/* Standard syntax */
@keyframes example {
	0%   {background-color:red; left:0px; top:0px;}
	25%  {background-color:yellow; left:200px; top:0px;}
	50%  {background-color:blue; left:200px; top:200px;}
	75%  {background-color:green; left:0px; top:200px;}
	100% {background-color:red; left:0px; top:0px;}
}
</style>
</head>
<body>

<p><b>Note:</b> This example does not work in Internet Explorer 9 and earlier versions.</p>

<div></div>

</body>
</html>
```
## transitions

###transition
: allows you to change property values, smoothly (from one value to another), over a given duration.
( provide a way to control animation speed when changing CSS properties)
:x
```html
<!DOCTYPE html>
<html>
<head>
<style> 
div {
	width: 100px;
	height: 100px;
	background: red;
	-webkit-transition: width 2s; /* For Safari 3.1 to 6.0 */
	transition: width 2s;
}

div:hover {
	width: 300px;
}
</style>
</head>
<body>

<p><b>Note:</b> This example does not work in Internet Explorer 9 and earlier versions.</p>

<div></div>

<p>Hover over the div element above, to see the transition effect.</p>

</body>
</html> 
```
###transition-timing-function
```
:specifies the speed curve of the transition effect.
:{values
	ease 		- specifies a transition effect with a slow start, then fast, then end slowly (this is default)
	linear 		- specifies a transition effect with the same speed from start to end
	ease-in 	- specifies a transition effect with a slow start
	ease-out 	- specifies a transition effect with a slow end
	ease-in-out - specifies a transition effect with a slow start and end
	cubic-bezier(n,n,n,n) - lets you define your own values in a cubic-bezier function
transition-delay 	Specifies a delay (in seconds) for the transition effect
transition-duration 	Specifies how many seconds or milliseconds a transition effect takes to complete
transition-property 	Specifies the name of the CSS property the transition effect is for
transition-timing-function 	Specifies the speed curve of the transition effect
```

## 2D Transforms
```css
- translate() 	: moves an element from its current position
		:x
			translate(50px, 100px);
- rotate ()		: rotates an element 
	:x  transform: rotate(20deg);
- scale()		: increases or decreases the size of an element
- skewX()		: skews an element along the X-axis by the given angle.
	:x
		div {
			-ms-transform: skewX(20deg); /* IE 9 */
			-webkit-transform: skewX(20deg); /* Safari */
			transform: skewX(20deg);
		}
- skewY()		: method skews an element along the Y-axis by the given angle.
- skew()		: skews an element along the X and Y-axis by the given angles.
- matrix() 		: combines all the 2D transform methods into one.
		The parameters are as follow: matrix(scaleX(),skewY(),skewX(),scaleY(),translateX(),translateY()):
		:x transform: matrix(1, -0.3, 0, 1, 0, 0);
```

## 3D Transforms
:allows you to format your elements using 3D transformations
```css
rotateX() method rotates an element around its X-axis at a given degree
rotateY() method rotates an element around its Y-axis at a given degree
rotateZ() method rotates an element around its Z-axis at a given degree
-cursor: pointer;//makes the mouse cursor look like hand
```

## process
### include a css in a html:
```html
<head>	<link rel="stylesheet" type="text/css" href="theme.css" />
</head> 
```
### embeding css inside html
```html
<style media="screen" type="text/css">
	Add style rules here
</style>
```
### Importing a CSS file from within CSS
```
This lets us attach a new CSS file from within CSS file itself. 
To import a new CSS file from within CSS simply use the following rule:
@import "newstyles.css";

-it is not seo friendly
	From a page speed standpoint, @import from a CSS file should almost never be used,
	as it can prevent stylesheets from being downloaded concurrently. For instance, if stylesheet A contains the text:
	@import url("stylesheetB.css");
	then the download of the second stylesheet may not start until the first stylesheet has been downloaded.
- If you need a stylesheet that depends on another one, use @import. Do the optimization in a separate step.
```
	
### rounded button + hover + font + shadow
```css
.button {
	background-color: #4BCD37;
	border: 3px solid;
	border-color: white;
	border-radius: 20px;
	padding: 15px 32px;
	text-align: center;
	text-decoration: none;
	display: inline-block;
	font-size: 16px;
	margin: 4px 2px;
	cursor: pointer;
		box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
}
.button:hover {
	background: #8db1c7;
	text-decoration: none;
}
```
### grouping selectors
```css
		It will be better to group the selectors, to minimize the code.
		h1, h2, p {
			text-align: center;
			color: red;
		}
```
### Striped Tables (even rows to another color)
		tr:nth-child(even) {background-color: #f2f2f2}
### Text in Transparent Box over an image
```css
<!DOCTYPE html>
<html>
<head>
<style>
div.background {
background: url(klematis.jpg) repeat;
border: 2px solid black;
}

div.transbox {
margin: 30px;
background-color: #ffffff;
border: 1px solid black;
opacity: 0.55;
filter: alpha(opacity=60); /* For IE8 and earlier */
}

div.transbox p {
margin: 5%;
font-weight: bold;
color: #000000;
}
</style>
</head>
<body>

<div class="background">
<div class="transbox">
This is some text that is placed in the transparent box.
</div>
</div>

</body>
</html>
```
### Full-height Fixed Vertical Navbar
```css
<!DOCTYPE html>
<html>
	<head>
	<style>
	body {
		margin: 0;
	}

	ul {
		list-style-type: none;
		margin: 0;
		padding: 0;
		width: 25%;
		background-color: #f1f1f1;
		position: fixed;
		height: 100%;
		overflow: auto;
	}

	li a {
		display: block;
		color: #000;
		padding: 8px 16px;
		text-decoration: none;
	}

	li a.active {
		background-color: #4CAF50;
		color: white;
	}

	li a:hover:not(.active) {
		background-color: #555;
		color: white;
	}
	</style>
	</head>
	<body>

	<ul>
	<li><a class="active" href="#home">Home</a></li>
	<li><a href="#news">News</a></li>
	<li><a href="#contact">Contact</a></li>
	<li><a href="#about">About</a></li>
	</ul>

	<div style="margin-left:25%;padding:1px 16px;height:1000px;">
	<h2>Fixed Full-height Side Nav</h2>
	<h3>Try to scroll this area, and see how the sidenav sticks to the page</h3>
	<p>Notice that this div element has a left margin of 25%. This is because the side navigation is set to 25% width. If you remove the margin, the sidenav will overlay/sit on top of this div.</p>
	<p>Also notice that we have set overflow:auto to sidenav. This will add a scrollbar when the sidenav is too long (for example if it has over 50 links inside of it).</p>
	<p>Some text..</p>
	<p>Some text..</p>
	<p>Some text..</p>
	<p>Some text..</p>
	<p>Some text..</p>
	<p>Some text..</p>
	<p>Some text..</p>
	</div>

	</body>
</html>
```
### Active/Current Navigation Link and Right-Align Links
```css
<!DOCTYPE html>
<html>
	<head>
	<style>
	ul {
		list-style-type: none;
		margin: 0;
		padding: 0;
		overflow: hidden;
		background-color: #333;
	}

	li {
		float: left;
	}

	li a {
		display: block;
		color: white;
		text-align: center;
		padding: 14px 16px;
		text-decoration: none;
	}

	li a:hover:not(.active) {
		background-color: #111;
	}

	.active {
		background-color: #4CAF50;
	}
	</style>
	</head>
	<body>

	<ul>
	<li><a href="#home">Home</a></li>
	<li><a href="#news">News</a></li>
	<li><a href="#contact">Contact</a></li>
	<li style="float:right"><a class="active" href="#about">About</a></li>
	</ul>

	</body>
</html>
```
### Dropdown Menu inside a Navigation Bar
```css
<style>
	ul {
		list-style-type: none;
		margin: 0;
		padding: 0;
		overflow: hidden;
		background-color: #333;
	}

	li {
		float: left;
	}

	li a, .dropbtn {
		display: inline-block;
		color: white;
		text-align: center;
		padding: 14px 16px;
		text-decoration: none;
	}

	li a:hover, .dropdown:hover .dropbtn {
		background-color: red;
	}

	li.dropdown {
		display: inline-block;
	}

	.dropdown-content {
		display: none;
		position: absolute;
		background-color: #f9f9f9;
		min-width: 160px;
		box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
	}

	.dropdown-content a {
		color: black;
		padding: 12px 16px;
		text-decoration: none;
		display: block;
		text-align: left;
	}

	.dropdown-content a:hover {background-color: #f1f1f1}

	.dropdown:hover .dropdown-content {
		display: block;
	}
	</style>
	</head>
	<body>

	<ul>
	<li><a class="active" href="#home">Home</a></li>
	<li><a href="#news">News</a></li>
	<li class="dropdown">
		<a href="#" class="dropbtn">Dropdown</a>
		<div class="dropdown-content">
		<a href="#">Link 1</a>
		<a href="#">Link 2</a>
		<a href="#">Link 3</a>
		</div>
	</li>
	</ul>

	<h3>Dropdown Menu inside a Navigation Bar</h3>
	<p>Hover over the "Dropdown" link to see the dropdown menu.</p>

	</body>
</html>
```

### Tooltip
```css
<!DOCTYPE html>
<html>
	<style>
	.tooltip {
		position: relative;
		display: inline-block;
		border-bottom: 1px dotted black;

	}

	.tooltip .tooltiptext {
		visibility: hidden;
		width: 220px;
		background-color: black;
		color: #fff;
		text-align: center;
		border-radius: 6px;
		padding: 5px 0;
		position: absolute;
		z-index: 1;
		bottom: 100%;
		left: 50%;
		margin-left: -60px;
		
		/* Fade in tooltip - takes 1 second to go from 0% to 100% opac: */
		opacity: 0;
		transition: opacity 1s;
	}

	.tooltip:hover .tooltiptext {
		visibility: visible;
		opacity: 1;
	}
	</style>
	<body style="text-align:center;">

	<h2>Fade In Tooltip on Hover</h2>
	<p>When you move the mouse over the text below, the tooltip text will fade in and take 1 second to go from completely invisible to visible.</p>

	<div class="tooltip">Hover over me
	<span class="tooltiptext">Tooltip text.sometimes we have lots of content<br>in many lines</span>
	</div>

	</body>
</html>
```

### focused input textboxes
```css
<!DOCTYPE html>
	<html>
	<head>
	<style> 
	input[type=text] {
		width: 100%;
		padding: 12px 20px;
		margin: 8px 0;
		box-sizing: border-box;
		border: 1px solid #555;
		outline: none;
	}

	input[type=text]:focus {
		background-color: lightblue;
	}
	</style>
	</head>
	<body>

	<p>In this example, we use the :focus selector to add a background color 
	to the text field when it gets focused (clicked on):</p>

	<form>
	<label for="fname">First Name</label>
	<input type="text" id="fname" name="fname" value="John">
	<label for="fname">Last Name</label>
	<input type="text" id="lname" name="lname" value="Doe">
	</form>

	</body>
</html>
```

### inputbox with image inside
```css
<!DOCTYPE html>
<html>
<head>
<style> 
input[type=text] {
	width: 100%;
	box-sizing: border-box;
	border: 2px solid #ccc;
	border-radius: 4px;
	font-size: 16px;
	background-color: white;
	background-image: url('searchicon.png');
	background-position: 10px 10px; 
	background-repeat: no-repeat;
	padding: 12px 20px 12px 40px;
}
</style>
</head>
<body>

<p>Input with icon:</p>

<form>
<input type="text" name="search" placeholder="Search..">
</form>

</body>
</html>
```

### thumbnail image as link
```html
<!DOCTYPE html>
<html>
	<head>
	<style>
	a {
		display: inline-block;
		border: 1px solid #ddd;
		border-radius: 4px;
		padding: 5px;
		transition: 0.3s;
	}

	a:hover {
		box-shadow: 0 0 2px 1px rgba(0, 140, 186, 0.5);
	}
	</style>
	</head>
	<body>

	<h2>Thumbnail Image as Link</h2>
	<p>Use the border property to create thumbnail images.<br>
	 Wrap an anchor around the image to use it as a link.</p>
	<p>Hover over the image and click on it to see the effect.</p>

	<a target="_blank" href="paris.jpg">
	<img src="paris.jpg" alt="Paris" width="400" height="300">
	</a>

	</body>
</html>
```
## Debugging CSS
```
 - Copy the code to your local machine and test it there before uploading it.
 - Shorten the code to its simplest form to seee if the problem exists.
 -press f12 in your browser to check and replace DOM elements and other things
 - replace your code with a working code from the internet.
  fortunately, css of all web pages in the internet can be viewed by right clicking and pressing 'view page source'
 ```
 
<h2>responsive pages</h2>
      
<pre>:Responsive Web Design is about using CSS and HTML 
        to resize, hide, shrink, enlarge, or move the content 
        to make it look good on any screen(desktops, tablets, and phones)
        
 Example
</pre>

```html
 <!DOCTYPE html>
 <html lang="en-us">
 <head>
 <style>
 .city {
 float: left;
 margin: 10px;
 padding: 10p;
 max-width: 300px;
 height: 300px;
 border: 1px solid black;
 }   
 </style>
 </head>
 <body>
    <h1>Responsive Web Design Demo</h1>
       <h2>Resize this responsive page!</h2>
            <div class="city">
            <h2>London</h2>
            <p>London is the capital of England.</p>
            <p>It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants.</p>
            </div>

            <div class="city">
            <h2>Paris</h2>
            <p>Paris is the capital of France.</p> 
            <p>The Paris area is one of the largest population centers in Europe, with more than 12 million inhabitants.</p>
            </div>

            <div class="city">
            <h2>Tokyo</h2>
            <p>Tokyo is the capital of Japan.</p>
            <p>It is the center of the Greater Tokyo Area, and the most populous metropolitan area in the world.</p>
            </div>

            <div class="city">
            <h2>New York</h2>
            <p>The City of New York is the most populous city in the United States.</p>
            <p>New York is an important center for international diplomacy and has been described as the cultural and financial capital of the world.</p>
            </div>

            </body>
            </html>
```

<h3>process</h3>
for whole page,include <meta> tag in your page:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

for elements of the page,one way is to use a responsive style sheet, like W3.CSS
        
<h4>      Float</h4>
<pre>
: is a CSS positioning property.
                    In a print layout, images may be set into the page such that text wraps around them as needed. 
                    This is commonly and appropriately called "text wrap".
                    In page layout programs, the boxes that hold the text can be told to honor the text wrap, or to ignore it.
                    Ignoring the text wrap will allow the words to flow right over the image like it wasn't even there.
                    This is the difference between that image being part of the flow of the page (or not). Web design is very similar.
                In web design, page elements with the CSS float property applied to them are just like the images in the print layout
                    where the text flows around them. 
                    Floated elements remain a part of the flow of the web page.
                    This is distinctly different than page elements that use absolute positioning.
                    Absolutely positioned page elements are removed from the flow of the webpage,
                    like when the text box in the print layout was told to ignore the page wrap.
                        Absolutely positioned page elements will not affect the position of other elements
                        and other elements will not affect them, whether they touch each other or not.
                
                Aside from the simple example of wrapping text around images, floats can be used to create entire web layouts.
</pre>

Example

```css
 #sidebar {
 float: right;			
 }
 ```
 ### :res
	http://www.w3schools.com/cssref/default.asp
	https://css-tricks.com/all-about-floats/
