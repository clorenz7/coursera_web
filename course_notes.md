# Week 1

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

