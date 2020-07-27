# Module 1: HTML

Resources:
- jsfiddle.net for providing sample code to folks
- codepen.io Includes a console/browser you can use, and you can save and share.
- css-tricks.com A great resource for HTML and CSS

What is HTML:
- HyperText Markup Language: Markup is for annotation/tags (tells what the content is)
- Human Readable: gives the document structure
- HTML gives the document structure
- CSS: Color Style, Sizes, Fonts, etc
- Javascript: Behavior and functionality

HTML History
- WHATWG evolves HTML, W3C keeps the HTML5 standard
- W3C has the standard on their website
- [CanIUse](caniuse.com) keeps track of HTML, CSS, JS APIs and their support on browsers
- W3C has a validator service
- w3schools has browser statistics and trends (Chrome is heavily used)

HTML tags
- opening tag, content, closing tag. Inside brackets is eleemnt name
- Linebreaks, horizontal rules only have opening tags
- tags can have attributes: name value pairs.
- id attribute must be unique
- space not allowed between < and element, need space before attributes, ignored everywhere else
- Attributes specified on opening tag
- Best practice is to put values in quotes, can us ' and "
- Self closing tags are possible `<p/>` == `<p></p>` but mostly useless in HTML5

HTML Document Structure
- Need to use HTML version declaration
- Title is required in head
- Body is the content to show the user, also known as viewport
- The file is interpreted sequentially from top to bottom.

HTML Content Models
- Which elements are allowed to be nested inside other elements.
- Block-level elements begin on a new line by default. Can contain in-line or other block-level elements (Flow content)
- Inline elements render on the same line by default. Can only contain other inline elements (phrasing content)
- HTML5 has more complex sets of categories, but these elements play well with CSS.
- div stands for division, span for span. div is generic block level element, span is generic inline element. div can have a span inside of it
- block level starts on a new line.
- Newlines in the HTML file do not correspond to what is rendered, the div and span do that.

Lec 6 Heading Elements
- semantic element: implies some meaning to the content (hints to the meaning) (may help with SEO)
- `<h1>` to `<h6>` headings are an example, giving importance (only structure, not style)
- We use divs to apply style.
- Header consists of company logo, tag line, etc. Sometimes `<nav>` for navigation.
- `<section>`, `<article>` typially goes inside the section, can have sections within articles. Also `<aside>`, `<footer>` all block level elements. They are meant to indicate structure of the document.

Lec7: Lists HTML Structure
- `<ul>` Unordered list tag (can only have li elements)
- `<li>` list item tag (can have a nested ul inside)
- `<ol>` Ordered List Tag
- Typically used for navigation portions of the webpage
- `<p>` is for paragraph

Lec 8: HTML Character Entity References
- Need to differentiate between syntax chars and content chars.
- 3 characters to always escape:
    - "<" &lt;
    - ">" $gt;
    - "&" &amp;
- Also of use &nbsp; "Non-breaking space" for line wrapping issues
- &quot; for quotation marks (get around UTF-8) issues

Lec 9: Creating Links
- `<a href="" title="">TEXT</a>` Can be a relative or absolute links. Title is used by screen readers for visually impaired. "a" is for anchor
- a is both an inline and block level element. You can wrap it around a div tag.
- using `target="_blank"` will open in a new tab/window
- Fragment identifier, `href="#section1"` will go to the section with the id "section1" or an anchor tag with a name field.
- Frag IDs used for single page applications.

Lec 10: Displaying Images
- `<img src="url" width= height= >`
- img is an inline element
- width and height are useful to visually partition the page so that it is not jumpy as the image loads. And in case the image does not load.
- option-cmd-i will open up chrome developer tools. You can throttle the DL speed in the network tab.
- Commenting in HTML: `<!--COMMENT -->`

# Module 2: CSS

Lec 11: Power of CSS (Cascading Style Sheets)
- HTML defines the structure of the content
- CSS provides styling capability: This is important to make it pleasing to the user, the user experience.
- CSS is very powerful: the same structure can be presenting in drastically different ways.
- Check out CSSzengarden.com: Same content, only the style changes.
- You can even do animations and such with CSS.

Lec 12: Anatomy of a CSS Rule
```css
p {
    color: blue;
}
h1 {
    font-size 20px;
}
```
- p is the selector (every paragraph tag)
- color is property, blue is value, prop:val is declaration
- Can apply multiple declarations
- A collection of these rules is a stylesheet
- You can add the CSS to an HTML file with the `<style>` tag of the head section.
- `width` property can be used to define how much screen space it takes up
- Each browser comes with default styles that it applies to common elements

Lec 13: Element, Class, and ID Selectors
- DOM: Document Object Model
- Selectors determine what set of elements to apply CSS to.
- The browser goes through the DOM to find those elements
- Element selector: specifying the element name (e.g. `p`)
- `.blue {}` define a CSS class named "blue" `<p class="blue">` accessed/declared with the "class" attribute
- `#name {}` defines an id selector. It is the name of some id: `<div id="name">`
- You can also group them: `div, .blue {}`

Lec 14: Combining Selectors.
- `p.big {}` selects every p that has class="big"
- `article > p {}` targets every p that is a *direct* child of an article element
- `article p {}` is a descendant selection: every p that is inside (at any level) of an article
- Multiple classes are applied to an element by listing them with a space between them
- Adjacent selector `+` Sibling selector `~`

Lec 15: Pseudo-Class Selectors
- Styles based on user interaction
- synatx: `selector:PseudoClassName` where PseudoClassName can be :link :visited :hover :active, ...
- links have states, which can be targeted by pseudoClasses....
- Can do things like make a button:
```css
a:link, a:visited {
    text-decoration: none;
    display: block;  %/ Makes it a block-level
    background-color: green
    margin-bottom: 1px
    width: 200 px
    text-align: center
}
a:hover, a:active {
    color: purple,
    background-color: red
}
```
- Active is when the user has clicked, but not released
- Can use `li:nth-child(3)` to get the 3rd element in a list
- Can do things like `nth-child(odd)`
- Pseudo selectors can be combined as well `div:nth-child(4):hover`
- Make sure that selectors are simple and readable
- Tricky example: ` a:hover div:nth-child(5){}` will modify the 5th element when any of the divs within the a element are hovered over.

Lecture 16: Style Placement
- Placement defines which style declarations override others
- You can place style directly in the element, e.g. `<p style="text-align:center;...">` this is in-line styling.
- To keep style consistent across many files, we need to use an external stylesheet: `<link rel="stylesheet" href="style.css">` in the `<head>` section
- The file just contains would would normally be between the `<style> </style>` areas.
- You almost always want all of your styles in the external file for a real-world site.

Lecture 17: Conflict Resolution
- cascading algorithm defines how to combine styles to determine which declaration should be applied. Which rule wins.
- origin precidence (when in conflict) - last declaration wins. HTML is processed sequentially, top to bottom. External CSS is declared at the spot where it's linked
- With no conflict, the declarations merge.
- Inheritance - children of a tag inherit properties. For example: Body is the top element, all children of the body will inherent properties from it.
- Specificity: "Most specific selector combination wins" In order of decreasing priority: inline, id, "class, pseudo-class", # of elements (e.g. `div p {}` = 2) You can think of each of these things as a 4-base score
- `!important` means ignore specificity and cascade, just apply it. This can quickly become dangerous on large projects

Lecture 18-19: Styling Text
- `font-family: "Times New Roman", Times, serif;` use multiple font options incase user computer doesnt have it.
- Use hex for colors `color: #0000ff`
- `font-style: italic; `
- `font-weight: bold` or `100,, 200, .. 900`
- `font-size: 16px` is common (these are pixels - absolute unit, but relative to viewing device if high DPI device)
- `text-transform: capitalize` uppercase, etc
- `text-align: right` left, etc
- `font-size: 120%` relative to browser default
- `font-size: 2em;` relative to width of letter M.
- You can chain multiple percent and em, it does not over-ride, they accumulate. You can also say 0.5em
- Doing a font-size percentage in the body is common as it sets overall size. Then use ems for relative in the document.
- Font size being relative helps with zooming in the browser.


Lectures 19-21
- In HTML, every element is considered a box.
- Besides content, each box has padding, border, and margin.
- `margin-bottom: 30 px`
- You can investigate the margin and border and such in the chrome developer tools element inspection.
- Can modify with `margin:0; padding:0`
- Example `padding: 10px 10px 10px 10px` to define top, right, bottom left paddings.
- Example `border: 3px solid black`
- A width of 300 px applies only to the content, not the other stuff. Have to account for margins, etc.
- For layout you want to account for the entire thing. CSS3 lets you use `box-sizing: border-box` to make it be 300px for the padding and border included.
- Modern frameworks use `border-box`, it is not inherited. You can do it with the star `* {}` selector. It is not inheritance, it is "select every element".
- Left and right margins are cumulative (additive) between two element. But top and bottom margins collapse: the larger margin wins.
- `user agent stylesheet` define defaults. CSS style resetting to override this is typically done with the star selector.
- The content can spill outside of your box if there is too much and you constrain the height.
- `overflow: visible` is the default, but `hidden` will clip. `auto` will add scroll bars as needed. `scroll` makes them always visible, even if not needed.


Lecture 20: The Background Property
- Can use `background-image: url("file_name")` to show an image where the file_name is relative to the CSS file.
- It will be repeated unless you use with `background-repeat`. image wins in terms of priority over the color
- Can use `background-position: bottom right`. Center is default.
- Can do all in one: `background: url("") no-repeat right center`

Lecture 21: Positioning Elements By Floating
- Most UIs are made by floating elements
- You do with `float: right`
- This takes them out of the regular document flow. They are positioned at the top left or right of the containing element. So other stuff will move up because the space is empty. That non-floated stuff will define the size of the container.
- With floating elements, margins no longer collapse
- Can use `clear:left` to say "nothing should be floating to the left of me"
- Can say `clear:both` to work with multiple elements, possibly of different sizes.
- When floated elements can't fit on the screen, it goes to the next line.
- By specifying the width as a percent in a div, and floating it, you can get a very flexible layout.

Lec 22: Rel and Abs Element Positioning
- Floating is an alternative positioning scheme.
- Static positioning: Normal document flow. Positioning offsets are ignored. Default for all elements, except html
- Relative positioning: offsets are from the original position. top, bottom, left, right are the properties. Element is not taken out of the normal document flow. Original spot is preserved (to the rest of the document, other stuff will not move).
- Example:
```css
p {
    position: relative
    top: 50px \\shift from top
    right: -50px \\equiv to left: 50px
}
```
- Absolute Positioning: All offsets are relative to the nearest ancestor which has posititioning set, other than static. html is the only element that has non-static positioning on it by default.
- Abs position element will be taken out of normal document flow and other elements act as if it doesn't exist.
- If container element is offset, everything inside is offset with it
- Need to set containing (parent) element to `position:relative` to get relative positioning work things to work


Lec 23: Media Queries
- Allow you to query elements based on their properties like width, etc
- The most common way of using CSS is for providing different layouts for different screen sizes
- Media query syntax:
```css
@media (max-width: 767 px) {
    p { color: blue;}
}
```
- It is a stylesheet in a stylesheet, "max-width" part is the "media feature", resolves to true of false. If true, style within applies.
- You can target orientation, screen, or print.
- max-width / min-width are most common: these refer to the width of the device.
- You can use logical operators: `(min-width:) and (max-width:)` A comma is an "or".
- You almost always start with a base style. Then target screen sizes with `@media` queries.
- Be careful not to overlap range boundaries (aka breakpoints) as multiple styles could apply.
- You can test other device sizes in teh chrome developer tools, and it shows the ranges of the media queries (click the phone loking thing)

Lec 24: Responsive Design
- A Responsive Web Site is designed to adapt its layout to the viewing environment by using fluid, proportion-based grids, flexible images, and CSS3 media queries.
- Make your website like water: "you put water in a cup, it becomes the cup"
- Using % is how you achieve fluid widths
- The layout adapts to the size of the device. Based on the width, typically.
- Content verbosity or visual delivery may change (show phone number more prominently on mobile, or make things hidden)
- As an alternative, you could have your backend server detect the user-agent and decide which version to serve up. m.mysite.com
- The most common layout is the 12-column grid responsive layout. 12 because of its factorability.
- Browser window is 100%, so 1 column is 8.33%
- You can even nest 12-column grid layouts within other columns, it is common
- You assign each div to multiple classes: `<div class="col-lg-3 col-md-6">` and the classes define the widths of the boxes. If the browser is too small, the lg class will not be applied. The above is a way to switch from each div taking a quarter of the screen to taking up half of the screen when screen gets small. If it gets too small, they will go to block level since float was defined in the media queries.
- Adding to the head `<meta name="viewport" content="width=device-width, initial-scale=1">` will prevent the mobile browser from adjusting the zoom, which it does by default.

Lecture 25: Intro To Twitter Bootstrap
- It is a popular HTML/CSS/JS framework
- It is mostly CSS classes
- Requires a particular HTML structure, just asks for a few extra divs
- JS framework is based on jQuery for plugins (depends on it)
- Mobile-first means plan mobile from the start, and CSS framework is mobile ready
- Disadvantages of Bootstrap? #1 - too big and bloated. Lots of features you won't use. You can use selective download.
- You have to add `css, fonts, js` folders.
- You download and unzip the minified Bootstrap, as well as jQuery
- Can use with `<link rel="stylesheet" href="css/bootstrap.min.css">`
- Add Bootstrap after jQuery with `<script src="js/bootstrap.min.js"></script>`
- Put your own CSS and scripts after these libraries.
- You can right click and do "inspect element"

Lecture 26: Boostrap Grid System
- You use something like this:
```html
<div class="container">
    <div class="row">
        <div class="col-md-4"></div>
```
- Can also use "container-fluid"
- Bootstrap applies some negative margins on row elements to align column content with other content
- `col-SIZE-SPAN` is the column identifier. SIZE=md, lg, etc. SPAN is how many columns the element should span (1 through 12) (e.g. col-md-4)
- Columns will collapse (stack) below SIZE width.
- `col-xs` will never collapse

# Module 3 - Coding a Static Site

Lecture 27: Client Visit
- Most clients have no ideas what they want, but don't know how to translate what they need to software.
- Bring web site examples of similar businesses
- They will have lots of important information. But not everything can be important: Less is MORE. Don't cram info.
- Find a way for the client to invest in the project, some skin in the game. Commit for something.
- Have one person responsible for decisions, so that you don't get conflicting demands
- Limit the number of (free) revisions upfront
- Google for web development client questionaire
- Can ask young people in school to do things for free for their resume (or small fee)
- Understand what client has right now

Lecture 28: Design Overview
- Worst thing to do is to start coding right away, you want to have layout mockups to present and get approval. Then you code.
- balsamiq.com is a mock up tool you can use (but it costs)
- You can check the components of the mockup in to a repository.
- It is best to use [Google fonts](http://google.com/fonts)
- Designer will give you color schemes (hex vals) and fonts.
- Photoshop is typically used by designers, but you can also use powerpoint.

Lecture 29: Overview of Setup
- Rules: use videos and source code
- Current lecture's before will contain previous lectures after as a starting point.
- if you go to `localhost:3001` you can see the UI for browsersync and configure it
- Use jquery-2.1.4 or greater and bootstrap
- Use google fonts to get the `<link>` you need to add to your page, and the proper family

Lecture 30: Navbar Header
- Use `--files "**/*"` to also capture changes to CSS.
- We can use symantic tag `<header>` for the navbar with `<nav>` tag. There are `class="navbar navbar-default"` from bootstrap
- Use `class="container"` to keep content width constrained, inside the nav element
- `class="navbar-header"` is good for a logo in upper left. You can look at the source
- Look at components in the bootstrap documentation.
- `<a>` makes something clickable. `<alt="logo image">` lets renderer know what something is
- You can use `backgound: url(...)` in the CSS to display the image as well
- `class="navbar-brand"` is another bootstrap element.
- `class=pull-left"` is the bootstrap way of doing float left
-  `text-transform:uppercase` makes it all uppercase. You can also do `text-shadow`
- You can disable underline with `text-decoration: none`. Need to specify with `.navbar-brand a:focus` and `a:hover`
- If we want an element to be visible at a particular size (breakpoint). You can use `class=visible-md`

Lecture 31: Collapsible Button Menu
- We use `<button type="button" class="navbar-toggle collapsed"` from Bootstrap to add the menu
- `data-` lets JS get at elements easily.

Lec 32: Coding Nav Menu Buttons
- `data-target=#collapsable-nav` makes the div with that id be visible
- Can use `<ul class="nav navbar-nav navbar-right">` to make the navbar and pull it to the right (a rightward going list)
- `<span class="glyphicon glyphicon-cutlery>` pulls in an icon font, a vector image that behaves like a font. These glyphicons come from bootstrap.
- `<br class="hidden-xs">` make the line break dissapear when the screen is small. You can also do this with text.
- `<a href="tel:410-602-5008">` is how you link to a phone call.
- `text-align: right` will make blocks of text align to the right
- Applying `clear:both` makes it so that the header color extends to all elements within the header.

Lec 33: Fixing Menus
- You can edit values (of width, etc) in the chrome dev tools!
- `font-size 5vw;` 5 % of viewport width


Lec 34: Coding the Jumbotron
- The jumbotron is the large picture in bootstrap
- We need a top level element `container` for the main content of the site.
- Emmit plugin allows you to write `div.container` and turn it into tags.
- We can use `class=img-responsive visible-xs` to change the size of the image with screen size, and the image only shows up in extra small.
- `no-repeat` is important for background images. Match image size to lowest width of media queries.
- `box-shadow` is cool for images
- You can uncheck properties in the chrome renderer.
- Specificity (number of classes when styling, eg `.container .jumbotron {}`) is important!

Lecture 35: Coding the navigation tiles
- Every bootstrap grid has be in a `container`
- Use `class=row` for navigation tiles holder. We can use the `class=col-md-4 col-sm-6` for the individual elements
- Can create a map with:
```css
<a href="" target="_blank">
    <div id="map-tile">
    <span>map</span> </div></a>
```
- `overflow: hidden` on the map-tile container is important to keep the map inside
- `#menu-tile:hover` with `box-shadow` is good for giving the user indication if they click
- `placehold.it` can be used to have image placeholders of various sizes
- `background-position: center;` allows you to keep the image centered as the container changes size.
- Can use `opacity: 0.8` to make them a little seethrough
- Google maps can give you an embedded (`<iframe>`) and link to the map
- Can right click and do "inspect" on an element
- Can center the tiles on the small screen where images are too small with ` width: 360px, margin 0 auto 15 px;`

Lecture 36: Coding the Footer
- It's a good practice to add what ends the div on the line with the closing tag
- Can use semantic tag `<footer class="panel-footer">` with a class=container inside, with a class=row inside. Then `<section>`
- Using `class="col-sm-4"` makes it have 3 columns for small or larger.
- `<hr class="visible-xs">` (horizontal rule) makes a horizontal line only when extra small.

Lecture 37: Coding the Menu Categories
- Can copy the index.html to make the menu-categories.html, and remove anything in the main content.
- There is a bootstrap class `text-center`
- Use `<section class="row">` to hold all of the tiles.
- `margin: 0 auto 15px` defines top, center, bottom, then implicitly the right to be centered since the left is
- `#menu-categories-title + div` means the next div sibling of that #id.
- You can copy styles from bootstrap classes if you want to make your own sizes

Lecture 38: The Single Menu Category Page
- You can do bootstrap grids inside of bootstrap grids!
- You can use `<li class="active">` to indicate that you are on that specific page.
- If the text gets too long in your grid, it can throw off all of the locations in your page.
- The problem is that the layout is based on floating to the left. We need to use the clear functionality. Look on bootstrap "responsive column resets". Use `<div class="clearfix visibile-md-block visible-lg-block">` inside of grid, after each even numbered element.
- The last thing is to dynamically insert content in to these pages

# Week 4 - Javascript

Lecture 40: Dev Env for JS
- Console tab (rather than elements) in Chrome dev tools gives you Javascript console
- You can write Js inside a `<script>*code here*</script>` tag. Or `<script src="js/script.js></script>`
- Script tags are executed sequentially.
- `var x = "Hello World!"`
- console.log() is how you write to console
- JS is a single threaded engine
- You can define JS in the body as well as the head.

Lec 41: Variables, Function, and Scope
- JS is dynamically typed language
- Function named a defined like:
```javascript
function a () {

}
```
or `var a = function () {...}`
- Both would be invoked with `a();`
- Arguments defined like `(x,y)`
- All arguements defined in a javascript function are optional!!
- In JS, functions define new scope. Vars and functions defined with global scope are available everywhere.
- Functions have a way of getting at the definitions in the functions in which they were created.
- This is the scope chain: everything in JS is executed in an execution context, and a function invocation creates a new context.
- Each EC has its own variable envioronment. And the `this` object, as well as a reference to its outer environment.
- Referenced variables will be searched for in the entire chain going out to global scope, relative to where the function is *defined*, not from where it is called!

Lec 42: Javascript Types
- A type is a particular data structure
- JS has 7 built-in types: 6 primitive, 1 object type
- An object is a collection of name/value pairs
- A value can be a nested object:
```javascript
name: "cory"
social: {
    linkedin: "cory",
    twitter: "corycory",
}
```
- Primitive type represents a single immutable value: not an object.
- Prim types: boolean, undefined (no value has ever been set [never do this to a var]: lacks definition), Null (signifies lack of value), Number (always a float64, no ints), String, Symbol (not covered in this class, new in ES6).
- `var x;` will result in x being `undefined` can do `(x == undefined)` to test.
- `undefined` means declared, but not defined. You can get "not defined" errors.


Lecture 43: Common Language Constructs
- string concat like python with `string += "World"`, etc.
- `undefined / 5` will output `NaN`. A `NaN` will typically represent an unspecified input variable to a function, which will result in it being `undefined`.
- You can do `var x=4, y=4;`
- `var x="4", y=4; x == y` will evaluate to `true`!!! This is type coersion, which forces types to be the same.
- You get around this with strict equality `x === y`
- What JS considers `false`: `null || undefined || "" || 0 || NaN`. (The or operation short circuits)
- You can use `Boolean(x)` to check the coersion of x.
Considered true: `true && "hello" && 1 && -1 && "false"` (The And operation also short circuits)
- In JS the best practice with curly braces is a matter of syntax.
```javascript
return
{
    name: "cory"
}
```
will actually return `undefined` since JS will add an implicit semicolon on the return statement.
- Semicolons are optional, but are considered best practice to use.
- For loop:
``` for (var i=0; i <10; i++) {}```

Lec 44: Handling Default Values
- Can do this (via type coersion) if x is not defined:
```javascript
function add5(x) {
    x = x || 3;
    return x + 5;
}
```

Lecture 45: Creating Objects
- An Object is a collection of name value pairs.
- Creation: `var company = new Object()`
- `company.name = "FB"` will create it.
- Have to do `company.ceo = new Object();` in order to do `company.ceo.name="Zuck"`
- Can also get at properties with `company["name"]` this allows you to have property names with spaces in them
- Object literal is a better way to do it:
```javascript
var fb = {
    name: "FB",
    ceo: {
        name: "Zuck",
        color: "blue"
    },
    "stock of company": 110 // NO COMMA!
}
```

Lecture 46: Functions Explained
- Functions are objects
- Functions are first-class data types. You can pass them around as inputs or outputs.
- You can set properties on functions!
- The value of the function is the actual code, you can do `func.toString()`
- So you can make a function factory that returns functions.

Lecture 47: Passing by value or by reference.
- Primitives are passed by value (copied), objects are passed by reference.
- The point is that for objects the memory location is passed by value / copied
- With functions, the input memory is copied, so objects are by reference, primitives by value

Lec 48: Function constructors, prototype and this keyword:
- `this` for a function points to the Global Window object. `window` is the global object.
- Capitalizing the first letter of a functio name lets you know it is a function constructor. But it kinda constructs an object.
- You can't return anything from the function.
- You can make them have methods!
```javascript
function Circle(radius) {
    this.radius = radius;
    this.getArea =
        function () {
            return Math.PI * Math.pow(this.radius, 2)
        };
}
var myCircle = new Circle(10); // is basically new Object()
```
- You can use a prototype to avoid having to make these functions over and over again by placing this outside of the Circle definition:
```javascript
Circle.prototype.getArea =
    function() {
        return Math.PI * Math.pow(this.radius, 2);
    }
```
- It will live inside of `__proto__` of the Circle object, so function will be shared.
- If you skip the `new` keyword, the Circle(10) will return undefined since that function returns nothing.

Lec 49: Object Literals and "this"
- Defining a function inside of a literal object, you can use `this` to get at the object.
- This is because `{} -> new Object()` and `new` redefines `this`.
- But a subfunction inside the literal object points to the global window!!!!
Get around the issue by:
```javascript
var self = this;

var inc = function() {
    self.radius = 20;
}
```

Lec 50: Arrays
- Can mix object types, example:
```javascript
var array = new Array()
array[0] = "Y";
array[1] = 2;
array[2] = function(name) {cosole.log(name);};
array[3] = {course: "HTML"};
```
- Shorthand notation: `var names = ["Y", "J", "J"];`
- `names.length` gives you the length
- Arrays can be sparse: `names[100] = "Jim";` will have undefined elements in between.
- There is a way to loop over objects:
```javascript
for (var prop in myObj) {
    console.log(prop + ":" + myObj[prop]);
}
```
- Can do this with arrays too:
```javascript
for (var name in names) {
    console.log("Hello" + names[name])
}
```
- If you have a property on the Array (it is an object!) it will also get printed in the above.

Lec 51: Closures
- Return doesn't really create its own context / reference / `this`
```javascript
function makeMultiplier (multiplier) {
    return (
        function(x) { return multiplier * x;}
    );
}
var doubleAll = makeMultiplier(2)
console.log(doubleAll(10)); // gets its own exec env
```
- So how does the `doubleAll` know the multiplier value is 2? Because of closures. JS preserves the outer lexical environment for the returned funcion in memory.

Lecture 52: Fake Namespaces
- Two scripts (JS files) with the same variable names can over-ride one another. Because they go in the global scope.
- We need to use namespaces, JS does not have them, so we hack them in:
```javascript
var Greeter = {};
Greeter.name = "Cory";
Greeter.sayHello = function () {
    console.log("Hello " + Greeter.name);
}
```
- Immediately Invoked Function Expressions (IIFEs)
```javascript
function a() {
    console.log("Hello");
}

// Alternately can run with:
(function() {
    console.log("Hello");
})();
```
- So you can write the entire Greeter stuff inside of an IIFE and pass in the window:
```javascript
(function (window) {
    var Greeter = {};
    Greeter.name = "Cory";
    Greeter.sayHello = function () {
        console.log("Hello " + Greeter.name);
    }

    window.Greeter = Greeter; // expose to outside
})(window); // IFFE with passing in the window
```

# Module 5: JS for Web Apps

Lec 53: DOM Manipulation
- Document Object Model (DOM)
- Found at `window.document` the document object contains the entire HTML page. This is how we can get at individual elements within the page.
- `document.getElementById("title")` it returns the `<h1 id="title"> Lecture 53</h1>`
- global scope is `window`, so in global scope, we can just use `document`
- Script is executed exactly where it is loaded, so all of the page might not be loaded.
- You can put the `<script>` at the end of the document to get around this.
- `document instanceof HTMLDocument`  returns true. There are many methods in that class.
- `<button onclick="sayHello()"> Say it! </button>` will call sayHello when the button is clicked:
```javascript
function sayHello () {
    var name = document.getElementById("name").value;
    var message = "Hello " + name + "!";
}
```
- You can have an empty div in your document `<div id="content" ></div>` and then retreive it:
```javascript
document
    .getelementById("content")
    .textContent = message;
```
Alternately to make the new text styled:
```javascript
document
    .getelementById("content")
    .innerHTML = "<h2>" + message + "</h2>";
```
- If we want to change other elements based on this, we can do:
```javascript
if (name === "student") {
    var title =
        document
            .querySelector("#title") // By CSS selector
            .textContent;
    title += " & Lovin' it!";
    // Need to set it since it is a primitive
    document
        .querySelector("#title") // or "h1"
        .textContent = title;
}
```
- There is also a queryAllSelector to get a list of things.

Lec 54: Handling Events
- Event handlers are function that are run based on events to an element. Can be things like `onfocus` `on keydown` `onblur` (when loses focus, ie click away)
- Can do function `sayHello (event)` which will cause `this` to point to the window object.
- Inserting this stuff in to your HTML is a bit messy (HTML is supposed to be about content), so you can use "unobtrusive event binding":
```javascript
document.querySelector("button")
    .addEventListener("click", sayHello);
```
which causes `this` to point to the containing (eg button) element.
- You can also do:
```javascript
document.querySelector("button")
    .onclick = sayHello;
```
- There is an event to run things before images or CSS are loaded.
```javascript
document.addEventListener("DOMContentLoaded")
    function (event) {
        // Define sayHello, add listeners, etc.
    }

```
which you can use to assign all of the event listeners.
- This ensures that all of the elements exist.

Lec 55: The Event Argument
- Looking at the event handler passed to the attached function
- Is a class like `mouseEvent` with a bunch of properties like coordinates, shift key status, etc.
- You can look up the API for these events on the http://developer.mozilla.org webpage
- There is a MouseMove event. So we can log the mouse location when it moves while the shift key is pressed.
```javascript
document.querySelector("body")
    .addEventListener("mousemove",
        function (event) {
            if (event.shiftKey === true) {
                console.log("x: " + event.clientX);
                console.log("y: " + event.clientY);
            }
        }
    );
```

Lecture 56: HTTP Basics
- Request/response stateless protocol. Response does not depend on previous requests. Server does not keep track of what the browser has done before.
- Client opens connection to server
- Client sends HTTP request for a resources
- Server sends HTTP response to the client
- Client closes connection to server
- URN: Uniform Resource Name: uniquely identifies resource or name of it, does not tell us how to get the resource. Example, this course: `HTML/CSS/Javascript/Web Developers/Yaakov/Chaikin` unique within the Coursera platform
- URI: Uniform Resource Identifier: Uniquely identifies resource or location of resource. Does not tell us how to get to the resource. example: `/official_site/index.html` It doesn't tell you where to get it (eg `coursera.org`).
- URL: Uniform Resource Locator: A URI that provides info on how to get resource. (eg `http://mysite.com/official/index.html`)
- Example GET request:
`GET /index.html?firstName=Cory HTTP/1.1`
GET: method
before ?: URI string
after ?: Query string
last part: version
- This is a URI because it is only issued after the browser connects to the server
(need to dial your number before you start talking)
- Methods:
GET: retrieves the resources, uses query string to pass data (not stored)
POST: Sends data to server in order to be processes (sent in message body)
- Response structure:
`HTTP/1.1 200 OK`
`version, code, english description`
Example larger response:
```
HTTP/1.1 200 OK
Date: Tue, 11 Aug 2004
Content-Type: text/html
<html>
<body> ...
```
- 200 is OK
- 404 is Not Found
- 403 is Forbidden (unauthenticated)
- 500 Internal Server Error (unhandled on server)

Lec 57: Ajax Basics
- AJAX: Asynchronous Javascript and XML
- Few apps use XML now, is mostly plaintext/HTML and JSON.
- Old web app flow was press button, get back entire new page, even for minor update
- In AJAX flow, the server replies teh small piece of data to insert. Faster response, less BW.
- Synchronous means one instruction at a time. Have to wait until a previous instruction as finished.
- With async you have separate threads or processes, so you run right away.
- JS is single threaded, how possible?
- JS engine is not only thing in the browser. There is also an event queue, and HTML rendering engine, webGL for graphics, and an HTTP requestor. The requestor is asynchronous.
- There is a special JS object to make the Ajax request. The response is not waited on. You pass in a JS function to handle the response (callback function).
- `request = new XMLHttpRequest()` is the object you use to make Ajax requests. Then use `request.onreadystatechange = function() {handleResponse(...);};`
- `request.open("GET", requestUrl, true)` sends it (if false, it is synchronous).
- `request.send(null);` sends it, `null` is for body of request.
- `request.readState == 4` means that you can process it. Should also check that `request.status == 200` before handling the response.
- You have to be careful with using global variables with these asynchronous requests! Race conditions! Which is why the onreadystatechange was wrapped in that anonymous function.
- You need to have the request handler /callback modify the HTML since it is asynchronous.

Lec 58: Processing JSON
- Simple textual representation of data. Easy for humans to read, and easy for machines to parse and generate. It is language independent.
- Subset of object literal syntax, but propert Names are in double quotes. String values are in double quotes.
- If you put single quotes around your JSON blob, you can have the JSON string in Javascript.
- JSON is not a Javascript Object literal, it is just a string.
- There is `var obj = JSON.parse(jsonString)` and `var str = JSON.stringify(obj)`

Lec 59: Mobile Nav Auto Collapse
- Want an event handler such that when the menu loses focus (`onBlur`) that the menu goes away.
- We have to use jQuery because it is a part of Bootstrap.
- `$` is the name of the jQuery function. it is the same as `document.addEventListener("DomContentLoaded")...`
- So, this code will process the `function()` when the HTML is loaded, but before styling:
```javascript
$(function() {
    $("#navbarToggle").blur( function(event){...
        $("#collapsable-nav").collapse('hide'); // jQuery defines collapse
    });
});
```
The event will basically be `DOMContentLoaded`
- `$("#navbarToggle")` is basically a query selector in jQuery, eg `document.querySelector("#navbarToggle").addEventListener("blur")`
- `window.innerWidth` is the width of the browser, not the monitor.

Lec 60: Dynamic Loading Home View Content
- Want to move towards an SPA (Single Page Application) by loading content dynamically.
- Don't need to reload page as they move around
- Need to remove all of main content of the home page and put it into a folder `snippets`
with a file `home-snippet.html`
- Links become onClick handlers.
- We insert the snipped into the main-content placeholder.
- Need a `showLoading` convenience method while the content is loading.... `http://ajaxload.info` lets you download GIFs for loading icons.
- Then you make a request for the HTML snippet above in order to insert it.
- XHR stands for XML/HTTP requests (or AJAX) on the network tab of Chrome Dev Tools, you can use that to see all of the requests


Lec 61: Dynamically Loading Menu Categories
- He deployed an app on Heroku!
- A REST API that supplies JSON data you need. The data sits as the davids-restaurant app on Heroku. It is Ruby on Rails, which is the backend.
- There is a single source (same origin) rule on browsers, which gets upset when you try to do AJAX calls from a different domain. It will block it.
- CORS (Cross Origin Resource Sharing) is the solution
- There are some HTTP headers which say it is safe to reach out to the other domain name
- Chrome dev tools has a preview tab that will display JSON really nicely.
- We use the JSON to generate HTML snippets that we insert
- The double curly braces are known as mustaches, which are targets for where data will go.
- You can fill in the string values with `string =string.replace(new RegExp(propToReplace, "g"), propValue)` g means replace everywhere you find.
- You can send Get Requests with (I think he wrote that wrapper though):
```javascript
$ajaxUtils.sendGetRequest(...)
```
- You can chain ajax requests inside of the callback of other requests

Lec 62: Dynamic Load of Single Category View
- `.toFixed(2)` will force 3.00 for the price.
- You can insert the `clearfix` CSS class with Javascript

Lec 63: Changing Active Button Style
- You do this by changing the CSS class of the button from home to menu as needed.

