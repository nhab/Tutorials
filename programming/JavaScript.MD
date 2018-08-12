 Is a high-level, dynamic, untyped, and interpreted programming language.

<h1>procedures</h1>

<h2>Refrencing it</h2>
  code example:

```html
 //save the code as  file:test.html 
 <script type="text/javascript">
    document.write ( new Date() );
</script>
```
<h2> including a javaScript file</h2>

```html
  <script type='text/javascript' src='Script1.js'></script>
```
<h2>Including from another js file :</h2>
   Put all the code using the remote library in the callback function.
               
  For example:

```javascript
function loadScript(url, callback)
{
    // Adding the script tag to the head as suggested before
    var head = document.getElementsByTagName('head')[0];
    var script = document.createElement('script');
    script.type = 'text/javascript';
    script.src = url;

    // Then bind the event to the callback function.
    // There are several events for cross browser compatibility.
    script.onreadystatechange = callback;
    script.onload = callback;

    // Fire the loading
    head.appendChild(script);
}
```
Then you write the code you want to use AFTER the script is loaded in a lambda function:

```javascript
var myPrettyCode = function() {

    // Here, do what ever you want
};
```
Then you run all that:

```javascript
 loadScript("my_lovely_script.js", myPrettyCode);

// Note that the script may execute after the DOM has loaded, or before,
//depending on the browser and whether you included the line script.async = false;
```
<h2>passing by reference parameter to function</h2>
 it can be implemented by passing object to function as parameter
 <h2>   events	</h2>	
   Example:
```html
<script type="text/javascript">
function checkRange(t,low,high) {
    var n = parseInt(t);
    if (t!="" && (isNaN(n) || n<low || n>high))
    alert("Enter a number between "+low+" and "+high);
}
</script>
<form> 
    <input type=text name=number size=10 onBlur="checkRange(this.value,1000,2000);">
</form>
```
<h2>'this' keyword</h2>
        you can use'this'  within a method to refer to the current object.
        accessing form elements by 'this'
            you could call validate in each form element's ' onchange event handler, using this to pass it the element, as in the following example:
```html
            <input type="text" name="age" size="3"
                onChange="validate(this, 18, 99)">
            which
                function validate(obj, lowval, hival) {
                    if ((obj.value < lowval) || (obj.value > hival)) {
                        alert("Invalid Value!");
                    }
                }
 ```
<h2> inheritance: </h2>
        is prototype-based:
        That means that there are no classes. Instead, an object inherits from another object.
        JavaScript is a class-less language. JavaScript is built on Objects rather than Classes. T
  
  Example:
```javascript
var animal = { eats: true }
rabbit = Object.create(animal)
alert(rabbit.eats) // true
 ```
<h2>    Prototype</h2>
        Every JavaScript object has a prototype. The prototype is also an object. 
        All JavaScript objects inherit their properties and methods from their prototype.
        
            Objects created using an object literal, or with new Object(), inherit from a prototype called Object.prototype.
            Objects created with new Date() inherit the Date.prototype.
            The Object.prototype is on the top of the prototype chain.
            All JavaScript objects (Date, Array, RegExp, Function, ....) inherit from the Object.prototype.
<h2>    raising events </h2>
        dispatchEvent is equivalent of raisevent in vb

Example
```javascript
            //in the function you want raise event,you call dispatchevent:
                x.onchange=function()
                {
                    x2.innerHTML=x.value;
                    
                    var event = new Event('chang');  // (*)
                    x.dispatchEvent(event);	
                }
                return x;
            ............................
            //in the place you want to use it,call addEventListener:
            // Listen for the event.
                ra.addEventListener('chang', function (e) {
                // e.target matches elem
                    alert(e.target);
                    console.log(e);
                }, false);
```

<h2>responsive pages</h2>
        :Responsive Web Design is about using CSS and HTML 
        to resize, hide, shrink, enlarge, or move the content 
        to make it look good on any screen(desktops, tablets, and phones)
        
 Example
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
            -for whole page,include <meta> tag in your page:
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
            -for elements of the page,one way is to use a responsive style sheet, like W3.CSS
        
      <h4>      Float</h4>
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

                Example
 ```css
                    #sidebar {
                    float: right;			
                    }
 ```
                    res:https://css-tricks.com/all-about-floats/
            css Grid System
                :
                    is a structure that allows for content to be stacked both vertically and horizontally
                    in a consistent and easily manageable fashion. 
                    Additionally, grid system code is project-agnostic 
                    giving it a high degree of portability so that it may be adopted on new projects.
                :{
                    - Rows are used to accommodate the columns.
                    - Columns make up the final structure and contain the actual content.
                    - Some grid systems will additionally include containers,
                        which serve as wrappers for the layout. 
                :processes
                    Resetting the Box Model
                        First and foremost, it is important for any grid system to reset the box model.
                        By default, the browser does not include the padding and border 
                        within the declared width and height of an element. 
                        This does not bode well for responsiveness. 
                        Thankfully, this can be fixed by setting the box-sizing property to border-box
                            for both rows and columns:

                        .row, 
                        .column {
                            box-sizing: border-box;
                        }
                        //Now we can leverage percentages for the widths of the columns.
                        //This allows the columns to scale upwards and downwards within different viewports
                        // while maintaining the structure
                    Clearing Floats
                        In order to align the columns horizontally, grid systems will float the columns. This means you need to clear the floating elements on the row to maintain the structure of the layout. This is where a clearfix comes in:

                        .row:before,
                        .row:after {
                            content: " ";
                            display: table;
                        }

                        .row:after {
                            clear: both;
                        }

                        By applying the clearfix to the row in your CSS, 
                        it will cause the row to stretch to accommodate the columns it contains without adding to the markup.
                    Defining Columns

                        For columns, the styles need to be defined in 2 parts: the common styles and the widths. First the common:

                        .column {
                            position: relative;
                            float: left;
                        }

                        Here, the column is given a relative position 
                        to allow any absolutely position content within the column to be positioned 
                        relative to that column. 
                        The column is then floated left for horizontal alignment
                        , which will cause the element to become display: block even if it did not start out that way.
                    Creating Gutters
                        Gutters help to create separation between columns for greater legibility and aesthetics. There are 2 schools of thought when approaching gutters; defining paddings within each column or using a percentage-based left margin for each column.

                        I prefer the latter approach because it facilitates responsive gutters that will remain relative to the columns and the viewport as a whole with different screen sizes. It also lets you define additional paddings for columns for further flexibility. The biggest advantage of padding-based gutters is in how they simplify calculations for column widths, which will become evident in the next section.

                        Using the percentage-based margin approach, we can target columns that are an adjacent sibling to a preceding column. This will create a left margin for every column except the first one, which we’ll define at 1.6% using the margin-left property:

                        .column + .column {
                            margin-left: 1.6%;
                        }
                    Calculating Column Widths

                        Before we can begin making calculations, we need to determine the maximum amount of columns per row. A popular choice is 12 as it boasts flexibility given that it is divisible by 1, 2, 3, 4, and 6. This permits a variety of different combinations that still allow for evenly distributed columns of the same size.

                        It’s important to understand that by going with a maximum of 12 columns per row, you need to fulfill that amount for every row regardless of how many columns you want. For example, if you wanted only a row of 3 equal columns, you would use 3 elements that each span 4 columns (4×3=12). Exceeding the sum of 12 will result in the extra column(s) wrapping to a new line.

                        Now that we know the maximum number of columns, next we need to determine the width of a single (1/12) column using the following formula:

                        scw = (100 – (m * (mc – 1))) / mc

                        Where:

                            scw = single column width
                            m = margin (1.6%)
                            mc = maximum columns (12)

                        When we plug in the numbers, we get a single column width of 6.86666666667%. From here we can use this number to calculate the rest of the column widths. The formula for this is:

                        cw = (scw * cs) + (m * (cs – 1))

                        Where:

                            cw = column width
                            scw = single column width (6.86666666667%)
                            cs = column span (1-12)
                            m = margin (1.6%)

                        Applying this formula for each of the 12 columns results in the following CSS.

                        .column-1 {
                            width: 6.86666666667%;
                        }

                        .column-2 {
                            width: 15.3333333333%;
                        }

                        .column-3 {
                            width: 23.8%;
                        }

                        .column-4 {
                            width: 32.2666666667%;
                        }

                        .column-5 {
                            width: 40.7333333333%;
                        }

                        .column-6 {
                            width: 49.2%;
                        }

                        .column-7 {
                            width: 57.6666666667%;
                        }

                        .column-8 {
                            width: 66.1333333333%;
                        }

                        .column-9 {
                            width: 74.6%;
                        }

                        .column-10 {
                            width: 83.0666666667%;
                        }

                        .column-11 {
                            width: 91.5333333333%;
                        }

                        .column-12 {
                            width: 100%;
                        }
                    Optimizing for Mobile Devices

                        Despite the fact that the grid system is responsive, it can only go so far. For devices with small viewports, such as smartphones, the width of the columns need to be adjusted to allow the content they contain to still appear legible and visually appealing. Media queries help with this:

                        @media only screen and (max-width: 550px) {
                            .column-1, 
                            .column-2, 
                            .column-3, 
                            .column-4, 
                            .column-5, 
                            .column-6, 
                            .column-7, 
                            .column-8, 
                            .column-9, 
                            .column-10, 
                            .column-11, 
                            .column-12 {
                                width: auto;
                                float: none;
                            }

                            .column + .column {
                                margin-left: 0;
                            }
                        }

                        Here, we are telling the grid to allow every column to take up the full width of its container for devices with a viewport smaller than 550px pixels wide. Since gutters are no longer necessary here, we remove those too.

                        Alternatively, you could opt for a mobile first strategy that takes the opposite approach, scaling upwards to a 12-column layout. In such a case, columns start as full-width, then we establish the column widths and floats to allow them to align horizontally as the screen resolution reaches a specified threshold. This is the preferred approach for Bootstrap’s grid system, which doesn’t institute the column widths until the viewport reaches a minimum width of 992 pixels. This may be a more favorable approach for your use case, and should be something to look out for when evaluating a grid system. 


            Viewport
                :is the user's visible area of a web page (in desktops, tablets, and phones).
                :processes
                    Setting The Viewport in html5
                        HTML5 introduced a method to let web designers take control over the viewport
                        , through the <meta> tag.
                        A <meta> viewport element gives the browser instructions 
                        on how to control the page's dimensions and scaling.
                        :x
                            <meta name="viewport" content="width=device-width, initial-scale=1.0">

                        // The width=device-width part sets the width of the page to follow the screen-width
                        // of the device (which will vary depending on the device).

                        // The initial-scale=1.0 part sets the initial zoom level 
                        // when the page is first loaded by the browser.
                    some best practices
                        1. Do NOT use large fixed width elements
                                - For example, if an image is displayed at a width wider than the viewport it can cause the viewport to scroll horizontally. Remember to adjust this content to fit within the width of the viewport.

                        2. Do NOT let the content rely on a particular viewport width to render well 
                            - Since screen dimensions and width in CSS pixels vary widely between devices, content should not rely on a particular viewport width to render well.

                        3. Use CSS media queries to apply different styling for small and large screens 
                            - Setting large absolute CSS widths for page elements, will cause the element to be too wide for the viewport on a smaller device. Instead, consider using relative width values, such as width: 100%. Also, be careful of using large absolute positioning values. It may cause the element to fall outside the viewport on small devices.
                

<h2>    Functions </h2>
        Definition :X:
                function myFunction(a, b) {
                    return a * b;
                }
                    
        usage	:x

                Right now, the time is
```javascript
<script type="text/javascript">
    var now = new Date();
    function pad2(i) {
        if (i<10) return "0"+i;
        return i;
    }
    document.write(pad2(now.getHours()),":",
    pad2(now.getMinutes()));
</script>
```
 <h3>       optional parameters</h3>
            you can call functions omitting some parameters and js will fil in the other parameters with the value undefined.
            <br>Example:
```javascript  
connect("www.google.com");  
function connect(hostname, port, method) {  
    // inside the function, 
    // hostname === "www.google.com", 
    // port === undefined,
    // method === undefined 
}
 ```
<h3>        Named parameters</h3>
            definition:
                function myFunction({param1, param2}={}){
                // ...
                } 
            usage:
                myFunction({ param1 : 70, param2 : 175});


 <h3>       -function scope</h3>
            All functions have access to the global scope.
 <h3>       -Invoking a Function as a Method </h3>
            X:
 ```javascript
                var myObject = {
                    firstName:"John",
                    lastName: "Doe",
                    fullName: function () {
                        return this.firstName + " " + this.lastName;
                    }
                }
                myObject.fullName();         // Will return "John Doe"
```
 <h3>       Function Expressions(anonymous function)</h3>
            :
                A function can also be defined using an expression 
                which  can be stored in a variable.
                then the variable can be used as a function:
            X:
```javascript
                var x = function (a, b) {return a * b};

                var z = x(4, 3);
```
  <h3>      Self-Invoking Functions(Anonymous Closures)</h3>
            :
                A self-invoking expression is invoked (started) automatically, without being called.
            advantages:
                -All of the code that runs inside the function lives in a closure, 
                which provides privacy and state throughout the lifetime of our application.
            X:
```javascript
                (function () {

                    var x = "Hello!!";      // I will invoke myself

                })();
```
<h3>        Immediately-Invoked Function Expression, or IIFE </h3>
            : executes immediately after it’s created.
            :X: 
                (function(){
                    // all your code here
                    var foo = function() {};
                    window.onload = foo;
                    // ...
                })();
        Parameter Defaults
            If a function is called with missing arguments (less than declared), 
            the missing values are set to: undefined

        The Arguments Object
            JavaScript functions have a built-in object called the arguments object.
            The argument object contains an array of the arguments used when the function was called (invoked)
        Nested Functions
            X:
                function add() {
                    var counter = 0;
                    function plus() {counter += 1;}
                    plus();    
                    return counter; 
                }

 <h3>       Closures</h3>

            :A "closure" is an inner function that has access to the outer function’s variables (and  parameters). 

            Creating:

                -You create a closure by adding a function inside another function.

                X:

                    function showName (firstName, lastName) {

                        var nameIntro = "Your name is ";

                            //# this inner function has access to the outer function's variables, including the parameter

                        function makeFullName () {       

                        return nameIntro + firstName + " " + lastName;   

                        }

                        return makeFullName ();

                    }

                    showName ("Michael", "Jackson"); //# Your name is Michael Jackson
 <h2>       Important ready Functions</h2>
            -getElementById
            -querySelector
                :Get the first element in the document with class="example":
                    document.querySelector(".example");
                res: http://www.w3schools.com/jsref/met_document_queryselector.asp
        

 <h2>   Arrays </h2>
    (var ar = [];)
        :PROC (methods / properties)
            defining an  array
                //you should initialize it as an empty array,in this way:
                //;then you can add members to it;
                //otherwise it would be empty instead of an object
                var outData=[];
            -Defining 
                use numbered indexes :
                    :X	 var ar = ["a", "b"];
                        var cars = ["Saab", "Volvo", "BMW"];
                or 		 var cars = new Array("Saab", "Volvo", "BMW");
                or You Can Have Different Objects in One Array
                    X:
                        myArray[0] = Date.now;
                        myArray[1] = myFunction;
                        myArray[2] = myCars;

            -Accessing 
                {X :
                    var name = cars[0];
                        cars[0] = "Opel";

            -Adding Elements  (by push function)
                :adds a new element at the end of an array :
                X:
                    var fruits = ["Banana", "Orange", "Apple", "Mango"];
                    fruits.push("Lemon"); 
                    or  
                    var fruits = ["Banana", "Orange", "Apple", "Mango"];
                    fruits[fruits.length] = "Lemon";  
            -removing Element by The pop() method 

                : removes the last element from an array
            -Deleting Elements
                ('delete' command is not recommended because 
                it make the element undefined
                instead use splice)
                X:
                    var fruits = ["Banana", "Orange", "Apple", "Mango"];
                    delete fruits[0];      // Changes the first element in fruits to undefined
            -splice()
                :
                add /removes items to/from an array at an specified index
                add X: 
                    var fruits = ["Banana", "Orange", "Apple", "Mango"];
                    fruits.splice(2, 0, "Lemon", "Kiwi");
                remove X:
                    var fruits = ["Banana", "Orange", "Apple", "Mango"];
                    fruits.splice(0, 1);        // Removes the first element of fruits

            -Copying array by value,for simple datatypes like string
                var newArray = oldArray.slice();
            -length
            -Array.isArray
                X:
                    Array.isArray(fruits);     // returns true

            -instanceof 
                X:
                    var fruits = ["Banana", "Orange", "Apple", "Mango"];

                    fruits instanceof Array     // returns true





            -sort()
            -NumericSort()  // '08' comes after '7'
            -reverse()
            -concat
                :for joining arrays

                    X:

                        var arr1 = ["Cecilie", "Lone"];

                        var arr2 = ["Emil", "Tobias","Linus"];

                        var arr3 = ["Robin", "Morgan"];

                        var myChildren = arr1.concat(arr2, arr3);     // Concatenates arr1 with arr2 and arr3

            -valueOf() 

                :It converts an array to a primitive value.

                -The valueOf() method is the default behavior for an array

<h2> Objects (var person = {};) </h2>
        :Objects are variables which have Membersber defined between { and }.
            members are either property or method.
            they are seperated by comma (,) .
        :{
            'property'
                : 
                    The "name :values" pairs are called properties.(or "key:value" pair)
                    X: (definition)
                        var person = {firstName:"John", lastName:"Doe", age:50};

                (Usage)
                    to access  property:
                        objectName.propertyName
                    
                    to create or access property
                        objectName["propertyName"]
        
            "method":
                    A property's value can be a function, 
                    in which case the property is known as a method.
                    :syntax
                        methodName : function() { code lines }
                    :X
                        var myObj = {
                            myMethod: function(params) {
                                // ...do something
                            }
                        };
                    :X2
                        <p id="demo"></p>
                        <script>
                        var person = {
                            firstName: "John",
                            lastName : "Doe",
                            id       : 5566,
                            fullName : function() {
                            return this.firstName + " " + this.lastName;
                            }
                        };

                        document.getElementById("demo").innerHTML = person.fullName();
                        </script>
        :process
            - Enumerating all properties of an object
                for..in loop :
                    for (var i in obj) {
                        if (obj.hasOwnProperty(i)) {
                            result += objName + "." + i + " = " + obj[i] + "\n";
                        }
                    }
                    
            - accessing keys of an object using Object.keys()
                var obj = { 0: 'a', 1: 'b', 2: 'c' };
                console.log(Object.keys(obj)); // console: ['0', '1', '2']

            - accessing values of an object using Object.getOwnPropertyNames()
                // Array-like object
                var obj = { 0: 'a', 1: 'b', 2: 'c' };
                console.log(Object.getOwnPropertyNames(obj).sort()); 
                // logs ["0", "1", "2"]

            - Deleting properties
                delete myobj.a;
                console.log ("a" in myobj) // yields "false"
            - Comparing Objects
                var fruit = {name: "apple"};
                var fruitbear = fruit;  // assign fruit object reference to fruitbear

                // here fruit and fruitbear are pointing to same object
                fruit == fruitbear // return true
                fruit === fruitbear // return true
            - Defining an object
                //you should initialize it as an empty object ,in this way:
                var outData={};
                :x
                    //you can initilize proerties;
                    var person = {   firstName:"John",    lastName:"Doe"};

<h2>    Classes</h2>
        :
            Creating class is simulated  
            by defining a JavaScript function 
            where	we then	 create an object using the 'new' keyword.

            'this' is used to  define new properties and methods for the object .
        {X
            Definition:
            
                function Car( model ) {
                    this.model = model;
                    this.color = "silver";
                    this.year = "2012";
                    
                    this.getInfo = function () {
                        return this.model + " " + this.year;
                    };
                }
            Usage:
                We can then instantiate the object using the Class constructor.
                
                var myCar = new Car("ford");
                myCar.year = "2010";
                console.log( myCar.getInfo() );
            
    
<h2>    modules </h2>
        :
            -Modules are files  to encapsulate a piece of code into a useful unit, 
            and how to register its capability/export a value for the module.
            -Modules may have name:
                define('myModule', ['dep1', 'dep2'], function (dep1, dep2) {
                    //Define the module value by returning a value.
                    return function () {};
                });

            -modules export a value, rather than define a type. 
            -In practice, most JavaScript modules export an object literal, a function, or a constructor. 
            Modules that export a string containing an HTML template or a CSS stylesheet are also common.
        ?:
            Defining:
                create asap.js file as:
                    var asap;
                    var isNode = typeof process !== "undefined" &&
                                {}.toString.call(process) === "[object process]";
                    if (isNode) {
                        asap = process.nextTick;
                    } else if (typeof setImmediate !== "undefined") {
                        asap = setImmediate;
                    } else {
                        asap = setTimeout;
                    }

                    export default asap;
            Usage:
                import asap from "asap";

                asap(function() {
                    console.log("hello async world!");
                });
        :X
            :x1
                There can be multiple named exports:
                //------ lib.js ------
                export const sqrt = Math.sqrt;
                export function square(x) {
                    return x * x;
                }
                export function diag(x, y) {
                    return sqrt(square(x) + square(y));
                }

                //------ main.js ------
                import { square, diag } from 'lib';
                console.log(square(11)); // 121
                console.log(diag(4, 3)); // 5

                You can also import the complete module:

                //------ main.js ------
                import * as lib from 'lib';
                console.log(lib.square(11)); // 121
                console.log(lib.diag(4, 3)); // 5

            :x2
                There can be a single default export. For example, a function:
                //------ myFunc.js ------
                export default function () { ··· } // no semicolon!

                //------ main1.js ------
                import myFunc from 'myFunc';
                myFunc();

                Or a class:

                //------ MyClass.js ------
                export default class { ··· } // no semicolon!

                //------ main2.js ------
                import MyClass from 'MyClass';
                const inst = new MyClass();


 <h2>   Scope</h2>
        :is the set of variables, objects, and functions you have access to.
        {:
            "Local"   Variables: 
                They can only be accessed within the function.

            "Global"  Variables:
                A variable declared outside a function, becomes GLOBAL.
                All scripts and functions on a web page can access it.
            -"Automatically Global":
                If you assign a value to a variable that has not been declared, 

                it will automatically become a GLOBAL variable.

                X:

                function myFunction() {

                    carName = "Volvo";

                }
    Globals
        implied globals
            : Whenever a name is used, the interpreter walks the scope chain backwards looking for a var statement for that name.
            If none is found, that variable is assumed to be global
            If it’s used in an assignment, the global is created if it doesn’t already exist.
            -This means that using or creating 'global variables in an anonymous closure' is easy. 
            disadvantage:
                this leads to hard-to-manage code, as it’s not obvious (to humans) which variables are global in a given file.
        Global Import
            :By passing globals as parameters to our anonymous function, we import them into our code,
            which is both clearer and faster than implied globals.
            X:
                (function ($, YAHOO) {
                    // now have access to globals jQuery (as $) and YAHOO in this code
                }(jQuery, YAHOO)); 
        Module Export
            :We can easily declare globals by exporting them, using the anonymous function’s return value.
            Doing so will complete the basic module pattern, so here’s a complete example:
            X:
                var MODULE = (function () {
                    var my = {},
                        privateVariable = 1;

                    function privateMethod() {
                        // ...
                    }

                    my.moduleProperty = 1;
                    my.moduleMethod = function () {
                        // ...
                    };

                    return my;
                }());
    


    deferred 
        :represents work that is not yet finished.
        a deferred represents the computation that results in the value
        :terms
            promise 
                :represents a value that is not yet known
                :is a placeholder for a result which is initially unknown 
        :{how it works
            deffered has promise.
            promise has :
                1.handler : what to do when the work is finished or value is known
                    $.then()
                2.states : pending,fulfilled,rejected
                    $.when()
    ajax
        :terms
            XMLHttpRequest  (XHR)
                : is an API used by web browser scripting languages 
                to transfer and manipulate XML data (or other formats like json) to and from a webserver using HTTP
                , establishing an independent connection channel between a  Client-Side and Server-Side of webpage.
                
                Methods
                    abort()
                        Cancels the current request.
                    getAllResponseHeaders()
                        Returns the complete set of HTTP headers as a string.
                    getResponseHeader( headerName )
                        Returns the value of the specified HTTP header.
                    
                    open( method, URL )
                    open( method, URL, async )
                    open( method, URL, async, userName )
                    open( method, URL, async, userName, password )
                        Specifies the method, URL, and other optional attributes of a request.
                        The method parameter can have a value of "GET", "POST", or "HEAD".
                        Other HTTP methods, such as "PUT" and "DELETE" (primarily used in REST applications) may be possible.
                        The "async" parameter specifies whether the request should be handled asynchronously or not.
                        "true" means that the script processing carries on after the send() method without waiting for a response,
                        and "false" means that the script waits for a response before continuing script processing.
                    send( content )
                        Sends the request.

                    setRequestHeader( label, value )
                        Adds a label/value pair to the HTTP header to be sent.

                Properties
                    onreadystatechange
                        An event handler for an event that fires at every state change.
                    readyState
                        The readyState property defines the current state of the XMLHttpRequest object.

                        The following table provides a list of the possible values for the readyState property:
                        State 	Description
                        0 	The request is not initialized.
                        1 	The request has been set up.
                        2 	The request has been sent.
                        3 	The request is in process.
                        4 	The request is completed.

                        readyState = 0 After you have created the XMLHttpRequest object, but before you have called the open() method.
                        readyState = 1 After you have called the open() method, but before you have called send().
                        readyState = 2 After you have called send().
                        readyState = 3 After the browser has established a communication with the server, but before the server has completed the response.
                        readyState = 4 After the request has been completed, and the response data has been completely received from the server.

                    responseText
                        Returns the response as a string.

                    responseXML
                        This property returns an XML document object
                        , which can be examined and parsed using the W3C DOM node tree methods and properties.

                    status
                        Returns the status as a number (e.g., 404 for "Not Found" and 200 for "OK").

                    statusText
                        Returns the status as a string (e.g., "Not Found" or "OK").

        :key concept
            1 - A client event occurs.
                : A  function is called because it is mapped to an event.
                :X
                    <input type="text" size="20" id="userid" name="id" onkeyup="validateUserId();">.

            2 - An XMLHttpRequest object is created.
                :X
                    var ajaxRequest;  // The variable that makes Ajax possible!
                    function ajaxFunction(){
                        try{
                            // Opera 8.0+, Firefox, Safari
                            ajaxRequest = new XMLHttpRequest();
                        }catch (e){
                        
                            // Internet Explorer Browsers
                            try{
                                ajaxRequest = new ActiveXObject("Msxml2.XMLHTTP");
                            }catch (e) {
                            
                                try{
                                    ajaxRequest = new ActiveXObject("Microsoft.XMLHTTP");
                                }catch (e){
                            
                                    // Something went wrong
                                    alert("Your browser broke!");
                                    return false;
                                }
                            }
                        }
                    }
            3 - request to the Webserver and callback
                :
                    a function that will be triggered by the client event  
                    and a callback function processRequest() will be registered.
                :X
                    function validateUserId() {
                        ajaxFunction();
                        
                        // Here processRequest() is the callback function.
                        ajaxRequest.onreadystatechange = processRequest;
                        
                        if (!target) target = document.getElementById("userid");
                        var url = "validate?id=" + escape(target.value);
                        
                        ajaxRequest.open("GET", url, true);
                        ajaxRequest.send(null);
                    }
            
            4 - The Webserver returns the result containing XML document.
                :You can implement your server-side script in any language, however its logic should be as follows.
                    1.Get a request from the client.
                    2.Parse the input from the client.
                    3.Do required processing.
                    4.Send the output to the client.
                :X
                    If we assume that you are going to write a servlet, then here is the piece of code.
                    public void doGet(HttpServletRequest request, HttpServletResponse response) throws IOException, ServletException 
                    {
                        String targetId = request.getParameter("id");
                        
                        if ((targetId != null) && !accounts.containsKey(targetId.trim()))
                        {
                            response.setContentType("text/xml");
                            response.setHeader("Cache-Control", "no-cache");
                            response.getWriter().write("true");
                        }
                        else
                        {
                            response.setContentType("text/xml");
                            response.setHeader("Cache-Control", "no-cache");
                            response.getWriter().write("false");
                        }
                    }
            5 - The XMLHttpRequest object calls the callback function and processes the result.
                :X
                    function processRequest() {
                        if (req.readyState == 4) {
                            if (req.status == 200) {
                                var message = ...;
                        ...
                    }
            6 - The HTML DOM is updated.
                :X
                    <script type="text/javascript">
                    <!--
                    function setMessageUsingDOM(message) {
                        var userMessageElement = document.getElementById("userIdMessage");
                        var messageText;
                        
                        if (message == "false") {
                            userMessageElement.style.color = "red";
                            messageText = "Invalid User Id";
                        }
                        else 
                        {
                            userMessageElement.style.color = "green";
                            messageText = "Valid User Id";
                        }
                        
                        var messageBody = document.createTextNode(messageText);
                        
                        // if the messageBody element has been created simple 
                        // replace it otherwise append the new element
                        if (userMessageElement.childNodes[0]) {
                            userMessageElement.replaceChild(messageBody, userMessageElement.childNodes[0]);
                        } 
                        else
                        {
                            userMessageElement.appendChild(messageBody);
                        }
                    }
                    -->
                    </script>
                    <body>
                    <div id="userIdMessage"><div>
                    </body>
        :process  examples
            :X post example
                var newName = 'John Smith',
                xhr = new XMLHttpRequest();

                xhr.open('POST',
                encodeURI('myservice/username?id=some-unique-id'));
                xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
                xhr.onload = function() {
                    if (xhr.status === 200 && xhr.responseText !== newName) {
                        alert('Something went wrong.  Name is now ' + xhr.responseText);
                    }
                    else if (xhr.status !== 200) {
                        alert('Request failed.  Returned status of ' + xhr.status);
                    }
                };
                xhr.send(encodeURI('name=' + newName));
            :X web api example
                var xhr = new XMLHttpRequest();
                xhr.open('PUT', 'myservice/user/1234');
                xhr.setRequestHeader('Content-Type', 'application/json');
                xhr.onload = function() {
                    if (xhr.status === 200) {
                        var userInfo = JSON.parse(xhr.responseText);
                    }
                };
                xhr.send(JSON.stringify({
                    name: 'John Smith',
                    age: 34
                }));
            
            :X UPLOADING using File Api
                var file = document.getElementById('test-input').files[0],
                xhr = new XMLHttpRequest();

                xhr.open('POST', 'myserver/uploads');
                xhr.setRequestHeader('Content-Type', file.type);
                xhr.send(file)
        :res 
            http://blog.garstasio.com/you-dont-need-jquery/ajax/
    events
        :term/functions
            Event bubbling
                Event bubbling directs an event to its intended target, it works like this:
                A button is clicked and the event is directed to the button. 
                If an event handler is set for that object, the event is triggered. 
                If no event handler is set for that object, the event bubbles up 
                (like a bubble in water) to the objects parent.
            addEventListener
                The document.addEventListener() method attaches an event handler to the document.
                syntax:
                    document.addEventListener(event, function, useCapture)  
            :process
                creating
                    var event = new Event('build');
                    // Listen for the event.
                    elem.addEventListener('build', function (e) { ... }, false);
                    // Dispatch the event.
                    elem.dispatchEvent(event);
    exception
        :x
            <script>
                try {
                    adddlert("Welcome guest!");
                }
                catch(err) {
                    document.getElementById("demo").innerHTML = err.message;
                }
                finally {
                    document.getElementById("demo").value = "";
                }
            </script>
    File operations
        -FileSystemObject Methods
            Add  (Folders)
                Adds a new folder to a Folders collection.
                :x
                    function AddNewFolder(path,folderName)
                    {
                        var fso, f, fc, nf;
                        fso = new ActiveXObject("Scripting.FileSystemObject");
                        f = fso.GetFolder(path);
                        fc = f.SubFolders;
                        if (folderName != "" )
                            nf = fc.Add(folderName);
                        else
                            nf = fc.Add("New Folder");
                    }

            BuildPath 
                Appends a name to an existing path.
            Close 
                Closes an open TextStream file.
            Copy 
                Copies a specified file or folder from one location to another.
            CopyFile 
                Copies one or more files from one location to another.
            CopyFolder
                Recursively copies a folder from one location to another.
            CreateFolder 
                Creates a folder.
            CreateTextFile 
                Creates a specified file name and returns a TextStream object that can be used to read from or write to the file.
            Delete 
                Deletes a specified file or folder.
            DeleteFile 
                Deletes a specified file.
            DeleteFolder 
                Deletes a specified folder and its contents.
            DriveExists 
                Returns true if the specified drive exists; false if it does not.
            FileExists 
                Returns true if a specified file exists; false if it does not.
            FolderExists 
                Returns true if a specified folder exists; false if it does not.
            GetAbsolutePathName 
                Returns a complete and unambiguous path from a provided path specification.
            GetBaseName 
                Returns a string containing the base name of the last component, less any file extension, in a path.
            GetDrive 
                Returns a Drive object corresponding to the drive in a specified path.
            GetDriveName 
                Returns a string containing the name of the drive for a specified path.
            GetExtensionName 
                Returns a string containing the extension for the last component in a path.
            GetFile 
                Returns a File object corresponding to the file in a specified path.
            GetFileName 
                Returns the last component of specified path that is not part of the drive specification.
            GetFileVersion 
                Returns the version number of a specified file.
            GetFolder 
                Returns a Folder object corresponding to the folder in a specified path.
            GetParentFolderName 
                Returns a string containing the name of the parent folder of the last component in a specified path.
            GetSpecialFolder 
                Returns the special folder object specified.
            GetStandardStream 
                Returns a TextStream object corresponding to the standard input, output, or error stream.
            GetTempName 
                Returns a randomly generated temporary file or folder name that is useful for performing operations that require a temporary file or folder.
            Move 
                Moves a specified file or folder from one location to another.
            MoveFile 
                Moves one or more files from one location to another.
            MoveFolder 
                Moves one or more folders from one location to another.
            OpenAsTextStream 
                Opens a specified file and returns a TextStream object that can be used to read from, write to, or append to the file.
            OpenTextFile 
                Opens a specified file and returns a TextStream object that can be used to read from, write to, or append to the file.
            Read 
                Reads a specified number of characters from a TextStream file and returns the resulting string.
            ReadAll 
                Reads an entire TextStream file and returns the resulting string.
            ReadLine 
                Reads an entire line (up to, but not including, the newline character) from a TextStream file and returns the resulting string.
            Skip 
                Skips a specified number of characters when reading a TextStream file.
            SkipLine
                Skips the next line when reading a TextStream file.
            Write 
                Writes a specified string to a TextStream file.
            WriteBlankLines 
                Writes a specified number of newline characters to a TextStream file.
            WriteLine 
                Writes a specified string and newline character to a TextStream file. 
        -reading text file x:
            <html>
                <head>
                <script>
                    var openFile = function(event) {
                    var input = event.target;

                    var reader = new FileReader();
                    reader.onload = function(){
                        var text = reader.result;
                        var node = document.getElementById('output');
                        node.innerText = text;
                        console.log(reader.result.substring(0, 200));
                    };
                    reader.readAsText(input.files[0]);
                    };
                </script>
                </head>
                <body>
                <input type='file' accept='text/plain' onchange='openFile(event)'><br>
                <div id='output'>
                ...
                </div>
                </body>
                </html>
            :res
                    http://www.javascripture.com/FileReader
        -reading text file regular way for IE
            <html>
                <head>
                <script>
                function ReadFile(fpath)
                {
                    var fso, f1, ts, s;
                    var ForReading = 1;
                    fso = new ActiveXObject("Scripting.FileSystemObject");
                    ts = fso.OpenTextFile(fpath, ForReading);
                    s = ts.ReadAll();
                    ts.Close();
                    return s;
                }
                function Read1()
                {
                    document.write("<pre>"+ReadFile("d:\\power-subconscious-mind.txt")+"</pre>");
                }
                </script>
                </head>
                <body>
                <button  onclick="Read1()">click</button>
            
                </body>
            </html>
        :res
            "javascript filesystem library"
                for linux?
                    https://github.com/vitillo/jsFS
                    https://ericbidelman.tumblr.com/post/14866798359/introducing-filerjs

:tools
    -alert(string);
    -f12 in browser to trace a js code in a page
    -console.log(obj); //you can watch the whole object in browser debugger
    -debugger; statement
        The debugger statement invokes any available debugging functionality,
        such as setting a breakpoint. If no debugging functionality is available,
        this statement has no effect.
    -jslint.com
        online page and js error detector
    -	jshint
        a tool that helps to detect errors and potential problems in your JavaScript code
    -ESLint
        terms
            Code linting
                is a type of static analysis that is frequently used to find problematic patterns or code that doesn’t adhere to certain style guideline
            lint 
                is a Unix utility that flags some suspicious and non-portable constructs (likely to be bugs)
                in C language source code; generically, lint or a linter is any tool that flags suspicious
                usage in software written in any computer language. 
            lint-like behavior
                is sometimes applied to the process of flagging suspicious language usage. 
                Lint-like tools generally perform static analysis of source code.
            Static program analysis
                is the analysis of computer software that is performed without actually executing programs
                (analysis performed on executing programs is known as dynamic analysis).
:res:
    http://www.2ality.com/
    https://developer.mozilla.org/en-US/docs/Web/JavaScript
    https://en.wikipedia.org/wiki/JavaScript#Features
    recommended book https://www.amazon.com/Professional-JavaScript-Developers-Nicholas-Zakas-ebook/dp/B006PW2URI?ie=UTF8&camp=1789&creative=9325&creativeASIN=B006PW2URI&linkCode=as2&redirect=true&ref_=as_li_tf_tl&tag=interhaptic-20
    recommended website http://bonsaiden.github.io/JavaScript-Garden/
    Nicholas C. Zakas videos https://www.google.com/search?q=Nicholas+C.+Zakas&num=100&client=firefox-b&source=lnms&tbm=vid&sa=X&ved=0ahUKEwi53IryoMzNAhXJq48KHR4IDz8Q_AUICSgC&biw=1525&bih=718&dpr=0.9
    debugging https://remysharp.com/2015/10/14/the-art-of-debugging
    http://www.javascripture.com/							
```
