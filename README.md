Permutation and combination
DFS and BFS,
DP,
Stack, quew , linklist, graph , arrays, 
sortest path algo.
Btree, bplus tree

https://learning.oreilly.com/videos/css-the/9781789954692/9781789954692-video1_1
https://learning.oreilly.com/videos/css-in-depth/10000MNLV201710
* By default "all CSS syntax is case-insensitive (...)" but there are some exception 
 CSS selector      | Case-sens. | Reference and notes
 ------------------|------------|--------------------
 id                | YES        |...
 name               | YES       |...
 element           | YES/NO     | ... YES for XML...
 class name        | YES        | [5]
 %url              | YES        | ...
 ----------------------------------------------------

# CSS
CSS decides how our content should look over the web page

### Three Ways to Insert CSS
-   Inline style: not recommended  
-   Internal style sheet: better then inline
-   External style sheet: good and recommended since it clearly separate our code with style

### CSS Selector
> CSS selector are the identifier that are used to identify the html element(s) that we want to style. It could be
- IDs selector  ex #id {}
- Class selector ex .class { }
- CSS attribute selector like [attribute] or [attribute*="value"] ex  [disabled] or button[class = 'btn-disabled']
```css
[disabled] {
color:red;
}
```
- Element (Tag name)selector : element {}
- `*`  (universal selector)  ex * {}
- above selector can also be combined with diff ways

### CSS cascading
*  Inline css has the highest priority
* #ID selector has the second highest priority
* class,pseudo claas and attribute selector has the same priority
* Element (Tag name) comes after class, pseudo class and attribute selector
* Universal selector (*) has the lowest priority
* css is overridden ie last last one overrides the first one, written in file

Note : if we use universal selector the all the css property of universal selector is applied to all element indivisually not inharitedd. It's used very rarely but I do use for 
```css
border-sizing: border-box // content-box is default
```
### Combinator

* Adjacent Sibling:  `h1 + P {color : red}` only p will red that comes just after h1
```
<h1>not applied>
<p>appied </p>
```
* General Sibling :  `h1 ~ P {color : red}` only p will red that comes at the same label of  h1
```
<h1>not applied>
<div> some other test</div>
<p>appied </p>
```
* Child : div > P {color : red}` only p will red that comes directly under div
```
<div> 
 <section>
   <p>not appied</p>
 </section>
<p>appied</p>
</div>
```
* Descendant: div  P {color : red}` only p will red that comes somewhere  under div
```
<div> 
 <section>
   <p>appied</p>
 </section>
<p>appied</p>
</div>
```
* class with specific element:  blow property will be appied with ancher tag that has an active class
```
a.active { 
  backgroup-color: blue;
}
```
### Groupign CSS : It's good if we need to apply same css to multiple selector

```
selector1, selector2 {
 color : red; //
}
```


## Chapter 2

### BoxModel 
In HTML there are two type of element 
 1. Inline : start with same line and width and height is same as it's content
 2. Block  : start with a new line  width is same as it's parent width.
 
**In html every element is treated as a box regardless of inline or block the only diff is inline element dont have effect of top and bottom margin/padding even they are applied**
* Shorthand properties is a combination of multiple properties in a single property ex
```
border : 2px solid black;
margin: 2px 2px 1px 1px; // top, right, bottom, left
```
* Width and height in percent of an element is calculated with respect to it's parent element.
*  by default width and height includes only content with and height, does not include margin, border and padding 
* Set the **property border-sizing : border-box** to include border and padding in width and height of element. Remember not margin
* **display: inline-block** is very important property, When we set it then the element not only behaves like inline element but also holds other property of block element like top and bottom margin etc
* **text-decoration:none** bacically use to removing underline from ancher tag while creating menus
* vertical-align: middle
* vertical-align: middle;
* text-align: center

* margin collapse : if we set margin in two adjecent element then margin are collapsed and the  bigger margin wins so to avoid this either use 'either margin-top or margin-bottom' and  'eithr margin-left or margin-right'.

#### Shorthand Properties

```css
border: 2px solid blue;
margin: 10px 5px 10px 5px;
```
### Pseudo Classes and Pseudo element.


**Pseudo classes**:  define the style of specific state of an element
```
a:hover{
color: while
}
a:active{ 
color: black
}
a:not(.active){ 
color: white;
}

```
**Pseudo element**: define the style of specific part of an element ex
```
p::first-latter {
font-waight: bold;
color: black;
}
```
### Grouping 
```
sele1, sel2 {
color: #ffff00;}
```
### Properties worth to remember
```
selector {
display: inline-block; //behaves like inline and also can set top, bottom margin and padding
text-decoration:none;
vertical-align:center;
color: black;
backgroup-color: while ;
padding:8px;
border: 2px;
margin: 10px;
width: 100px
height:100px;
text-align:center;
border-redius: 50%; //good for creating circle also set same widht and height
list-style: none;
font-waight:bold;
}
```

### Multiple Class: 
we can add multiple classes on a single element and these classes are applied  ( overridden ) in the same order in which they are written in css file. No matter in which order they are applied in html file
* **!important** : it can be used with any property and has highest priority
* **outline** is border like property but not actually border. basically comes after the border but before the margin, it appears while we the element has focus, it does not have it's own widths and height and does not a part of box model.
* **float: right** : it float the element to right side and also remove the element form document flow.
*  **solution off  float**:   use clear property after the float elment like **clear :both**

### Postioning of an element
 **static, fixed, relative, absolute, sticky**
 * default value of position is static ie **position: static**. 
 * An element with `position: fixed;` : Means position is calculated with respect to viewport (means it always stays in the same place even if the page is scrolled) and element is also removed from document flow
 * An element with `position: absolute;` Means positioned is calculated with respect to the nearest ancestor element that has possition property  and element is removed from  document flow, If no ancestor ele that has position probperty then it's position is calculated with respect to html element
 * An element with `position: relative;` Means positioned is calculated with respect to the it's original position  and element is removed from  document flow
 * A sticky postition is a conbination of `relative` and `fixed`
 * **z-index: 1** : z-index is used to bring any element up or down with respect to it's parent,  it works only with element having position property 
 * overflow:hindden : This hides the children element/content if it goes beyond the container
 * text-overflow : sets how hidden overflow content is signaled to users. It can be clipped, display an ellipsis ('…'), or display a custom string.It is applied only when overflow is hidden
 ```
 div {
  white-space: nowrap; 
  width: 50px; 
  overflow: hidden;
  text-overflow: ellipsis; 
  border: 1px solid #000000;
}
```

## 7 Background Image:
 Images says more then thousands words
```css
backgroup-image : url (location of image);
backgroup-size : 100px (only width)// 100px 200px; (width and height)
backgroup-size: 100% //it actually strach the image and fit as per the container size. Image is not cropped and sometime it looks bit odd.
backgroup-size: cover //zoom the image in correct ration of x and y and fill the container. sometime image is cropped but visible image look good.
backgroup-repeat : no-repeat / repeat-x/y;
backgroup-color: red;
position: relative;
backgroup-position: 20px; //20px from left side
```

### backgroup-position  
 With this property we can position the image as expected position

```css
backgroup-position : 20px // image is moved to right by 20px;
backgroup-position: 10% 20% //image is moved 10% from left and 20% from top.
backgroup-position: left top;//means image left and top corner would be fit to left and top of container
backgroup-position: left 10% bottom 20% // image will be cropped 10 % from left and 20% from bottom
backgroup-position: center;
```
### Background shorthand theory
background is the shorthand for all background property like
```css
background : url (home.jsp) cover//is one for all as all below
background-image: url(location)
background-size : cover; //etc
```
### Background origin and clip
background-origin and background-clip is same as border-sizing
```css
backgroup-origin: border-box;
box-shadow:  10px 10px;
 //_offset-x_ _offset-y_ _blur-radius_ _spread-radius_ _color_ to get bit 3D effect
text-shadow: 5px red;
```	 
* We can use img tag to show the images but it has less cantrol like cant set widt/height etc property easily 
* If we need to add widht/height properties to img tag then first set it inline-block
### linear-gradient it's a function which is used to spread the color.
* similar to linear-gradient we have radial-gradient, It spread the color in elliptical 
 ```css
 background : linear-gradient(top, red, blue);//many more combination are there
```
### Multiple Background 
We can use multiple background at the same time like linear-gradient with transparent attribute and image url.
Using gradient with image url will give diff look to image etc

### filter
Filte are used to change the visual effect of an element Filters are commonly used to adjust the rendering of images and backgrounds.

```
.filter-me  {  filter: <filter-function> [<filter-function>]* | none }
div {
 filter: blur(10px); 
}
```
-   blur()
-   brightness()
-   contrast()
-   drop-shadow()
-   grayscale()
-   hue-rotate()
-   invert()
-   opacity()
-   saturate()
-   sepia()
-   url() - for applying SVG filters


### 8 Size and Unit
* Pixel : px
* Parentage : %
* root em : rem
* em  : em
* Viewport Height: vh
* Viewport Width : vw

### There are three rule to remember of when widht/height is given in %
* Parentage is calculated with respect to it's parent
* when element's position is fixed then % is calculated with respect to viewport.
* when element position is absolute then % is calculated with respect to nearest ancestor content width+padding having position attribute as relative, fixed, sticky also could be absolute.
* when element position is static or relative then % is calculated with respect to nearest block label element
* By default font properties are set by brwoser so generally I avoid it to set for whole whole, Yes sometime we can set it for specific element.
* To make our site more dynamic we can use em/rem rather then px.
* 1em = current font size of that element (suppose cirremt font size of element 16px then 1em =16px)
* if cirremt font size is not defined of an element then em is calculated with respect to it's nearest parent size. When the size is calculated with respect to it's parent then  sometime it become diff and that's why we avoid to many em.
* 1rem = font size of root element (html element)
* if we do not set font size on root element then it's calculated based on browser defined font size which is good.
* em/rem can also be applied to other properties also ex padding, margin etc
* he vw and vh units. These units allow you to specify sizes in terms of percentages of the viewport width and viewport height.
* vmin : vw/vh whichever is smaller
* vmax : vw/vh of whichever is higher.

#### Min/Max 
generally we do use min-widht/height and max-widht/height to make our page responsive


#### In css there are properties to choose and they depend on requirement but in general we chose below.
|Property| Recommended |
|----------|----------|
|font-size |rem (use em only for children)|
| padding and margin | rem|
|border| px|
|width or heigh|either % or vw/vh in specific case px|
| top, bottom, left and right|perfer %|


### CSS with JavaScript
 
#### Concept of dialog 
 
**Note** : Below same approach we do use to show/hike left nevigation menu bar in mobile and other small devices

* create a backdrop with display:viewport and background dim color
```css for backdrop
 .backdrop { 
 position:fixed;
 z-index:100;
 display:none;// block
 width: 100vw;
 height;100vh;
 filter: blur(10px); // set background
 background: rgba(0,0,0.5);
 }
```
* Create one div wtih specified size and position and z-index.
 .dialog {
   position:fixed;
   display: block//none
   width:80vw;
   height:80vh;
   z-index: 200;   
 }
* Add click event on backdrop and model and also add show and hide function to model object
  ```js
  var hideModel = function(){
     document.querySelector('.backdrop').style.display= none;
     document.querySelector('.dialog').style.display= none;
  //document.querySelector().classList.remove('open'); //better approach for adding multiple properties

  });
  document.querySelector('.backdrop').addEventListener("click", showModel);
  document.querySelector('.model').addEventListener("click", showModel); 
 //Add a showModel function to model object
 var showModel = function(){
  document.querySelector('.backdrop').style.display= block;
  document.querySelector('.dialog').style.display= block;
  //document.querySelector().classList.add('open'); //better approach for adding multiple properties
 });
 document.querySelector('.dialog').showModel = showModel
  ```
* when we open a dialog, open backdrop also  so that we can avoid clicking on screen other then dialog.
 ```
    // call showModel function when we need to open dialog
    opendialog(){
	   showModel();
	}	
 ```

#### Change display property dinamically
* browser make an object of html page is called DOM and provide the ref of that as document.
* we can use combinator with querySelector like `document.querySelector('body .backdrop')` 
* querySelector select the first element.
* we can select all by 'querySelectorAll()'
 ```js
var el = document.querySelector(".backdrop"); // the first element in the document with the class "backdrop" is returned
el.style.display = 'block';
```
##### What if we need to add multiple css properties 
```css
.open {
  display: block!important;
  overflow: hidden;  
 }

el.className = 'open'; // This will actually overwride the complete class list means already existing classes will be removed
el.classList.add('open'); // This will actually not overwride the complete class list,add the new class to already existing classes.
el.classList.remove('open');
 ```

#### CSS properties notation

When we access any CSS property in JavaScript then dash is replaced by Next Capital latter or use quote inplace of dot. Some common css properties

ex.
```js
var node;
node.style.backgroundColor = "red"; 
// Or
node.style['backgroupd-color'] = "red"

```

```css/js
|CSS|	JavaScript|
|-----|----|
background	background
background-attachment	backgroundAttachment
background-color	backgroundColor
background-image	backgroundImage
background-position	backgroundPosition
background-repeat	backgroundRepeat
border	border
border-bottom	borderBottom
border-bottom-color	borderBottomColor
border-bottom-style	borderBottomStyle
border-bottom-width	borderBottomWidth
border-color	borderColor
border-left	borderLeft
border-left-color	borderLeftColor
border-left-style	borderLeftStyle
border-left-width	borderLeftWidth
border-right	borderRight
border-right-color	borderRightColor
border-right-style	borderRightStyle
border-right-width	borderRightWidth
border-style	borderStyle
border-top	borderTop
border-top-color	borderTopColor
border-top-style	borderTopStyle
border-top-width	borderTopWidth
border-width	borderWidth
clear	clear
clip	clip
color	color
cursor	cursor
display	display
filter	filter
float	cssFloat
font	font
font-family	fontFamily
font-size	fontSize
font-variant	fontVariant
font-weight	fontWeight
height	height
left	left
letter-spacing	letterSpacing
line-height	lineHeight
list-style	listStyle
list-style-image	listStyleImage
list-style-position	listStylePosition
list-style-type	listStyleType
margin	margin
margin-bottom	marginBottom
margin-left	marginLeft
margin-right	marginRight
margin-top	marginTop
overflow	overflow
padding	padding
padding-bottom	paddingBottom
padding-left	paddingLeft
padding-right	paddingRight
padding-top	paddingTop
page-break-after	pageBreakAfter
page-break-before	pageBreakBefore
position	position
stroke-dasharray	strokeDasharray
stroke-dashoffset	strokeDashoffset
stroke-width	strokeWidth
text-align	textAlign
text-decoration	textDecoration
text-indent	textIndent
text-transform	textTransform
top	top
vertical-align	verticalAlign
visibility	visibility
width	width
z-index	zIndex
```

### 10. Responsiveness


* Viewport meta tag : it actully adust  the site as per the device.
* MediaQueries : it actually change the design (By updating CSS) of site as per the viewport size/device size, It's like if stmt in css to apply css for specific condition liek @media (max-widht=650px)
* orientation probperty is very important in media query since orientation swap the widht and height
* In case of multiple media queries, it's applied from top to bottom. 
* It's always suggested to write media query in assending order
* better to keep media query block after common css

```mq
// below css will be applied only if min widht is 400px and orientation is landscape
#media (min-widht:400px) and (orientation:landscape) {

}

//, behaves like or same as applying same css to multiple element combinator
#media (min-widht:400px), (orientation:landscape) {

}

```

### Design page layout
```css
.header {
height : 2.5rem;
}
.footer {
height : 3.5rem;
}
.main {
min-height : calc(100Vh- 2.5rem-2.5rem); //do remember  substract margin also if we add
}

```
 #### Design Mobile First
  If your site is customer facing then we need to design our website mobile first to make it available to maximum custoemr since now a days maximum ppl (as per the survays approx 70 to 80%) are using mobile to use site and all.
  
  
 ###Styling form 
 
 #### Attribute Selector
 
 * `[type]` : any element with has type attribute
 * `[type='email']`  :element has type = email
 * `[lang ~= "en-us"]` :element has lang attribute "en-us" value in list lang list ex <p lang = "en-us en-uk">
 * `[lang |= 'en' ]` : element has lang attribute match "en" ex :   <p lang = "en-us">
 * `[href ^= '#']` : element has href attribute start with "#"
 * `[herf $= '.cd']` : element has herf attribute suffix with ".cd" 
 * `[href *= 'te' i]` : element has  attribute containg "te" value, I represent case insensitivity


* each element has default (browser provided) css we can overwride it.
* Understand that outline is different then border.we can overwride default/browser provided  outline.
* Add validation class dynamically by using JS

### Working with Fonts

* By default browser provide the font but we can overwride it.
* We can also define our own font family and use it by 
    1) Load the font from server at index page and use it.
```
  font-family : 'Montserrat', "sans-serif" //Browser first try to find Montserrat, if Montserrat is not found then sans-serif is applied
```	

* We have locally installed fonts at our machie, Using local font is not a good way because some fonts can be available at window machine but not on mac or linux.
    - https://www.cssfontstack.com/ : Check diff fonts available at diff machine
* Web fonts is a gret way, like google fonts.
    - https://fonts.google.com/
* We can just add font link in html file or import in CSS file and then add `font-family` tag to use it

```
<link href="https://fonts.googleapis.com/css?family=Roboto&display=swap" rel="stylesheet"> //or
@import url('https://fonts.googleapis.com/css?family=Roboto&display=swap'); //or
@import url('https://fonts.googleapis.com/css?family=Roboto:400,900&display=swap');
font-family: 'Roboto', sans-serif;
```

* We can design our own font also and use them like
```css
@font-face {
  font-family: myFirstFont;
  src: url(sansation_light.woff2), //web open font format (W3C crecogmandation provides better compression), true type font
       url(sansation_light.woff)
	   url(sansation_light.ttf);
	   
}
and use it
div {
  font-family: myFirstFont;
  font-size: 24px;
  latter-spacig: 3px;
  font-waight: 300;
  line-height: 40px;
  text-decoration: underline/overline/line-through;
  text-shadow: 1px 1px 2px pink;
}
```
* We can also use font shorthand like below
```
font: 15px arial, sans-serif;
```

* font-display : it could be swap, block or fallback
    - swap : means browser first apply the default font and once the actual font is loaded it is replaced 
	- block : browser will keep the space untill the font is loaded, once loaded it will be applied
```css
@font-face {
  font-family: myFirstFont;
  src: url(sansation_light.woff2);
  font-display: swap/block
	   
}
```

## Flexbox

* When we set `display:flex` the respective element is converted in flex container or parent 
* All the items inside it is called flex items or children
* flex-direction : defines the main  and cross asis, 
     ex :1. In case of flex-direction:row, maix axis is x and cross axis is y.
	     2. In case of flex-direction:colom; main axis is y and cross axis is x. 
* flex-wrap: wrap the flext items in defined container size
* flex-flow : shorthand for flext direction and flex wrap;
* justify-content: justify the content in main axis;
* align-items: aling the itmes in cross axis of flex-direction, occupy whole space
* align-content: align the flex lines in cross axis not flex items
#### Flex parent properties 
```css
.flex-container{
display: flex;
flex-direction: row/column/row-reverse //default is row
flex-wrap: wrap; // default is nowrap
flex-flow: row wrap; //  short form for flex-direction and flex-wap
justify-content:space-between; //very imp value to justify the element to occupy whole space. ex one div in left and another on right
align-items: center; //strach(default),flex-start, flext-end
align-content: flex-start;
}
```

* order : define the order of flex element in a flex or grid container
* align-self: align the specific item inside flex container in cross axix
* flex-grow:  It specifies how much of the remaining space in the flex container should be assigned to the item, default value is 0;
* flex-shrink:  If the size of all flex items is larger than the flex container then items are shrinked to fit according to flex-shrink, default value is 1
* flex-basis: it could be with or height in order to main axis.ie if flex-direction is row then flex-basis is similar to width and if flex direction is column then flex-basis is similar to height;
* shorthand for flex-grow, flex-shrink and flex-basis is flex;
#### Flex items properties 
```
.flext-item {
flex:
align-self:
order: 1 //default value is 0
flex-grow: 2;
flex-shrink:.5;
flex-basis: 300px
flex: 0 1 auto; 
}
```

### Flex Grid
Grid; It allows us to to create two  dimentional (row and column ) layout. unlike flex is one dimentional layout

#### Grid container
* display:grid; // it convert the element into grid
* grid-template-row: Defines the rows in grid;
* grid-template-column:  Defines the column in grid; ex 2fr 50px 1fr 1fr;
* we can give single or multiple names to row or column number in square bracket preceding to value. ex. [row-1-start] 100px
* we can use gird-template: grid-template-row/grid-template-column  shorthand instead of row and column template
* we can set gap in between rows and columns like grid-row-gap: 5px; and grid-column-gap:5px;
* we can also use grid-gap instead of grid-row-gap and grid-column-gap; like grid-gap: 20px 10px;
* use can give name to whole grid by using grid-template-area;
* fit-content: is very useful propery it adjust the width and height as per the content
* justify-item : justify the items in their grid cells in main axis
* align-item: align the items in their grid cells in cross axis.
* justify-content: aling the whole grid area not it's cell or cell's content in main axis;
* align-content: aling the whole grid area not it's cell or cell's content in cross axis;
* if we do not define rows or define less rows then grid explicitlly add the rows
```css
grid-container {
 display:grid;
 grid-template-columns: 40px 50px 2fr 1fr;
 grid-template-rows: 25% 100px fit-content(8rem); //min 8 rem and could be more if content require it more

 grid-template-column: repeat(4,25%);
 grid-template-rows: 100px minmax(20px, 200px); auto; //auto will occupy all remaining space
 grid-template-rows: [row-1-start] 100px [row-1-end row-2-start] minmax(20px, 200px) [row-2-end];
 grid-template: repeat(3,1fr) / repeat(4, 1fr) //three row and 4 column layout
 grid-template-area: "header header header" "sidebar main main main" "footer footer footer footer"
 grid-row-gap: 5px;
 grid-column-gap: 10px;
 grid-gap: 5px 10px; // shorthand or grid-gap:5px; 
 justify-items: strach // default 
 align-items: strach;
 justify-content: center;
 align-content:center;
}
```
#### grid children
* grid-row-start;   <line number>  
* grid-row-end : <line number>   // -1 indiacate last column  number
* grid-column-start:<line number> or span <number of column>
* grid-column-end: <line number>
* We can also use shorthand property like grid-column : 1/3; instead of using grid-column-start:1 and grid-column-end:3
* grid-area: topleft point and bottom right; //shorthand for all column and row
* grid-area: header //name of the area
* justify-self : align self in x axis
* align-self : align self in y axis
Above properties deinfe the position of an element inside grid; 


```css
.grid-element {
  grid-row-start: 1; //row-1-start
  grid-row-end: 3; // row-1-end
  grid-column: 1/3; //or 1/span 2 
  gird-column-start: 1;
  grid-column-end: 3; //-1 means occupy whole till last  || span 3 means upto next 3 column
  grid-area: [row-1-start]/[column-1-start]/[row-1-end]/[column-1-end]
  grid-area: header
}
```

* When rows and column can be overlap in grid.

* elements that are not a part of document flow are also not a part of grid.

## CSS transform: 

* **tranform** used to rotate the element.
* default rotation of element is center but we can change it by using transform-origin probperty.
* translate(xvalue,yValue), translateX and translateY, translateZ is used to shift the element in x and y direction after rotation
* we can use skew(), skewX or skewY to rotate the element.
* perspective probperty enable us to look the element from z persfective

```css
 
 .badge {
    tranform: rotateZ(45deg) translateX(20px) translateY(-5px);
	tranform: rotateZ(45deg) translate(20px, -5px)
	transform-origin: left top
    perspective: 100px; 
 }
```
### Transitions
* Transitions enable you to define the effect how an element is goes from one state to another.

```css
.addEffect {
   width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
   }
div:hover {
  width: 300px;
}
addEffect:hover {
  width: 300px;
}
input[type=text] {
  width: 100px;
  transition: width .5s ease-in-out;
}

input[type=text]:focus {
  width: 250px;
}

```
 ### @keyframes:
 * By using keyframes we do achieve animation by applying diff set of css at diff stages.
 * animation is also have predefined js events 1.animationStart, 2. animationEnd, 3. animationIteration,
 
 ```keyframes
 div {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
  animation: mymove 5s infinite;
}

@keyframes mymove {
  0%   {top: 0px; left: 0px; background: red;}
  25%  {top: 0px; left: 100px; background: blue;}
  50%  {top: 100px; left: 100px; background: yellow;}
  75%  {top: 100px; left: 0px; background: green;}
  100% {top: 0px; left: 0px; background: red;}
}
 ```

### Writing future proof CSS
* CSS variable : not supported by IE till 14;
 
```
:root {
  --main-bg-color: coral;
}

#div1 {
  background-color: var(--main-bg-color);
}

#div2 {
  background-color: var(--main-bg-color);
}
```
### Vender Prefix : 

generally diff browser implement diff feature with diff way and with diff speed so to use browser specifc browser provide css with some prefix.

* we can use https://autoprefixer.github.io/ site adds vender specific prefix

```prefix

display : -webkit-flex; // it will be execute only by firefox (webkit is actually earlier version of firefox), rest browser will ignore it.
display : -ms-flex;  //for microsoft ie
```

### @Support

CSS has a neat feature that allows us to test if the browser supports a particular property or property:value combination before applying a block of styles — like how a @media query matches
```
@supports (display: grid) {
  .main {
    display: grid;
  }
}
```
### Polyfills
Polyfills are generally a library or piece of code. ex babel.js, sessionStorage.js  etc
thre are feature that are supported by newer browser but not old one so to enable the support of these feature in older browser polyfills can be used.

Polyfill are not available for all feature like for grid there is no polyfills.
I would suggest think twoice to use polyfills for soe complex feature
```object.assing

if (typeof Object.assign !== 'function') {
  // Must be writable: true, enumerable: false, configurable: true
  Object.defineProperty(Object, "assign", {
    value: function assign(target, varArgs) { // .length of function is 2
      'use strict';
      if (target === null || target === undefined) {
        throw new TypeError('Cannot convert undefined or null to object');
      }

      var to = Object(target);

      for (var index = 1; index < arguments.length; index++) {
        var nextSource = arguments[index];

        if (nextSource !== null && nextSource !== undefined) { 
          for (var nextKey in nextSource) {
            // Avoid bugs when hasOwnProperty is shadowed
            if (Object.prototype.hasOwnProperty.call(nextSource, nextKey)) {
              to[nextKey] = nextSource[nextKey];
            }
          }
        }
      }
      return to;
    },
    writable: true,
    configurable: true
  });
}
```
### Eliminate Cross-Browser INconsistencies

Thre are browser which has diff implementation of diff feature like default font size, font family , margin, padding,  box sizing etc and that's why our site looks diff in diff browsers.
To normalize CSS we can use normalize.css file. but generally we dont use it because there are planty of feature which we dont use there are also there in this file and it unnecessory increase the page size also

### How to name CSS classes**

* use kebab-case, dont use cameelCase since it's case insensitive 
* use underscore to go inside, like main-nav_item means items is inside main navigation bar

### Vanilla CSS vs Frameworks
### Advantage:
* when we use CSS provided by specification 
* we have full control.
* No unnecessory (extra code) code 
#### Disadvantages:
* Build everything from the scratch
* have to manage cross browser compatibility
* Bit diff to manage same uniform look across the browser
  
#### 
  Yes framewoks like Bootstrap or Tailwind the great advantage like
   - Rapid development
   - Works well across the browser
   - Supported by maximum browser also so we 
   - Uniform look across the browsers


### SASS and SCSS 
* In our project we do use build tool task that actually convert our scss file into css file while coding itself
* Ayntacically Awesome Style Sheets
* Browser does not understand it, During development only we do convert it into css by using some tool
* Because of many good feature we do use scss like
     > Feature import, nexting, mixin, partials, variable, conditions, loop, function, inharitance, define rules
* Install saas `npm install -g sass`	 
* scss does not have semicolumn and curly bracess, scss has this (css like syntax)
* We can add watch like `scss --watch main.scss:main.css` to convert scss into css instinctly once scss is changed.
* SASS has built in function also like darken(#b37399, 20%) lighten(#b37399, 20%) etc
* SASS also support simple airthmatic operations like *, /,+,-
* Import and partials: 
    > CSS import will be handled by browser and that means it will take extra network call.
	> Partials: It's a way of spliting one big file into multiple small files by using import, 
	   In partials we do create files start with underscore. and can also be imported by only name without underscore.
```scss
//Variable
$main-color: #52157; // Variable
$border-default: .5px solid $main-color; // List Variable
$colors: (main: #23232, secondary: #232323); //Map

nav {
  //Nexting
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
    li{ 
	    display: inline-block; 
		border: $border-default;
		color: $main-color;
		colom: map-get($colors, main);
	  }
  }
}
```
* Wtih SASS we can import the way of writing media queries, We can write media queries inside element css like	   
```scss
. div {
   widht:100px;
  /* Extra small devices (phones, 600px and down) */
   @media only screen and (max-width: 600px) { widht:20px;} 
  }
```
* We can use inharitance by using @extends <classname>
```scss
.main-color {
color: blue;
}
.header {
extends .main-color //inharitance
height:20px;
}
```
* Mixins : Mixins are the kind of custom function and can be used using include keyword

```mixin
@mixin important-text($font-size) { //minxin
  color: red;
  font-size: $font-size;
  font-weight: bold;
  border: 1px solid blue;
  @media (max-widht:300px){
      width:$font-size/2;
  };
    @media (min-widht:300px){
      width:$font-size;
  }
}
.danger {
  @include important-text(25px);
  background-color: green;
}
```
* we can use & to use connected selector (.button:hover,button:active) like below
```&
.button {
 &:hover,
 &:active{color: blue;}
}
```
Note : mixin is better then inharitance (extends) because mixin can accept argument also like function

END