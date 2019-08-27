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
```
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
 
**In html every element is treated as a box regardless of inline or block the only diff is inline element dont have effect of top and bottom margin even they are applied**
* Shorthand properties is a combination of multiple properties in a single property ex
```
border : 2px solid black;
margin: 2px 2px 1px 1px; // top, right, bottom, left
```
* Width and height in percent of an element is calculated with respect to it's parent element.
*  by default width and height includes only content with and height, does not include margin, border and padding 
* Set the **property border-sizing : border-box** to include border and padding in width and height of element.
* **display: inline-block** is very important property, When we set it then element behaves only like inline but also holds other property of block element like top and bottom margin etc
* **text-decoration:none** bacically use to removing underline from ancher tag while creating menus
* vertical-align: middle

* vertical-align: middle;
* text-align: center

### Pseudo Classes and Pseudo element.


**Pseudo classes**:  define the style of specific state of an element
```
a:hover{
color: while
}
a:active{ 
color: black
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
display: inline-block;
text-decoration:none;
vertical-align:center;
color: black;
backgroup-color: while ;
padding:8px;
border: 2px;
margin: 10px;
width: 100px
height:100px;
}
```


### Multiple Class: 
we can add multiple classes on a single element and these classes are applied  ( overridden ) in the same order in which they are written in css file. No matter in which order they are applied in html file
* **!important** : it can be used with any property and has highest priority
* **outline** is border like property but not actually border. basically comes after the border but before the margin, it appears while we the element has focus, it does not have it's own widths and height and does not a part of box model.
* **float: right** : it float the element to right side and also remove the element form document flow.
*  **solution off  float**:   use clear property after the float elment like **clear :both**

### Positioning the element :
 * default value of position is static ie __position: static__. 
* different values for position
 **static, fixed, relative, absolute, sticky**

*  An element with `position: relative;` is positioned relative to its normal position
 * An element with `position: fixed;` is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled, also element is removed from document flow
* An element with `position: absolute;` is positioned relative to the nearest positioned ancestor and element is removed from it's original document flow
* A sticky element toggles between `relative` and `fixed`

* **z-index: 1** : z-index is used to bring any element up or down with respect to it's parent,  __it works only with element having position property__.


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
backgroup-position: 10% 20% //image is cropped 10% from left and 20% from top.
backgroup-position: left top;//means image left and top corner would be fit to left and top of container
backgroup-position: left 10% bottom 20% // image will be cropped 10 % from left and 20% from bottom
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
### linear-gradient it's a function which is used to spread the color.
* similar to linear-gradient we have radial-gradient, It spread the color in elliptical 
 ```css
 background : linear-gradient(top, red, blue);//many more combination are there
```
### filter
It can be used to achieve varying visual effects, 
```
.filter-me  {  filter: <filter-function> [<filter-function>]* | none }
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
*  PIXEL : px
* Parentage : %
* root em : rem
*  em  : em
* Viewport Height: vh
* Viewport Width : vw

### There are three rule to remember of when widht/height is given in %
* when element's position is fixed then % is calculated with respect to viewport.
* when element position is absolute then % is calculated with respect to nearest ancestor content width+padding having position attribute as relative, fixed, sticky also could be absolute.
* when element position is static or related then % is calculated with respect to nearest block label element
* By default font properties are set by brwoser so generally I avoid it to set for whole whole, Yes sometime we can set it for specific element.
* To make our site more dynamic we can use em/rem rather then px.
* 1em = current font size of that element (suppose cirremt font size of element 16px then 1em =16px)
* if cirremt font size is not defined of an element then em is calculated with respect to it's nearest parent size. When the size is calculated with respect to it's parent then  sometime it become diff and that's why we avoid to many em.
* 1rem = font size of root element (html element)
* if we do not set font size on root element then it's calculated based on browser defined font size which is good.
* em/rem can also be applied to other properties also ex padding, margin etc
* he vw and vh units. These units allow you to specify sizes in terms of percentages of the viewport width and viewport height.
* vmin : hundredths of whichever is smaller
* vmax : hundredths of whichever is higher.

### In css there are properties to choose and they depend on requirement but in general we chose below.
|Property| Recommended |
|----------|----------|
|font-size |rem (use em only for children)|
| padding and margin | rem|
|border| px|
|width or heigh|either % or vw/vh in specific case px
| top, bottom, left and right|perfer %|

### CSS with JavaScript
 
 ```js
var el = document.querySelector(".myclass"); // the first element in the document with the class "myclass" is returned
el.style.display = 'block';
 ```
### Concept of dialog

* Create one div wtih specified size and position and z-index.
* create a backlet with display;viewport and background dim color
* when we open a dialog open backlet also  so that we can avoid clicking on screen other then dialog.

to be continue...
https://learning.oreilly.com/videos/css-the/9781789954692/9781789954692-video9_1