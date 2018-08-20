Describes how HTML elements are to be displayed
## Terms and concepts
<b>padding : </b> Distance between borders  and <b>neighbouring</b> objects.
<b>Margin : </b>Distance between borders and <b>internal</b> objects.
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
to f
