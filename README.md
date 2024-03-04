# Css-units
## Absolute Units
Absolute units do not change. Think of them as permanent; once you set a particular element with an absolute unit, it will never change, regardless of the screen size it’s on. Examples of absolute CSS units include:

- Pixels (px)<br>
- Milimeters (mm)<br>
- Centimeters (cm)<br>
- Inches (in)<br>
- Points (pt)<br>
- Picas (pc)<br>

## Relative Units
Unlike absolute units, relative CSS units allow elements to vary based on the size of their parent element.
For example, if we have a button inside a parent div container, setting the width of the parent to 500px will affect the size of the button.
Below are the frequently used relative units that we’ll discuss:

- Element (em)
- Root Element’s Font Size (rem)
- Percentages (%)
- Viewport width (vw)
- Viewport height (vh)


### Element
When using Element (em), the font sizes of child elements depend on the font size of their parent element.

```html
<section>
        <p id= “first” >Css Units</p>
        <p id= “second” >Measurement Units</p>
        <p id= “third”>Mathematics</p>
</section>
```
In the code snippet above, we can see that the three paragraphs are all children of the section element.
```css
section{
 font-size: 20px;
}
#first{
 Font-size:2em; /*40px*/
}
#second{
 Font-size:1em; /*20px*/
}
#third{
 Font-size:0.5em; /*10px*/
}
```
In the stylesheet above, the parent element (section) has a font size of 20px. Each paragraph has a unique font sizes that depends on the font size of the parent element.
1em always equals the font size of the parent element. This makes it easy to calculate the font size of each child element in CSS units.
The font size of the first paragraph is 40px ( 20px * 2em = 40px).
Of the second paragraph, 20px ( 20px * 1em = 20px).
The font size of the third paragraph is 10px ( 20px * 0.5em = 10px).

### Root Element’s Font Size
Unlike em, which points to a particular parent element, rem points directly to the root element (html).
Generally, browsers set their font sizes to 16px. So if we set an element’s dimensions in rem, they can be calculated as so:
1rem = 16px
2rem = 32px

Example:
```css
#first{
 Font-size:2rem; /*32px*/
}
#second{
 Font-size:1rem; /*16px*/
}
#third{
 Font-size:0.5rem; /*8px*/
}
```
### Percentages
Just like em units, values with percentages depend on the value of the parent element’s CSS units.
```css
section{
 width:100%;
}
#first{
 width:50%;
}
#second{
    width:30%;
}
#third{
 width:10%;
}
```
In the code snippet above, the parent element has a width of 100%. All elements have a width of 100% by default; I have explicitly added “100%” in this example to give more context.
The first paragraph’s width is set to 50%, so it is 50% of the width of the parent element.
If we view this webpage on a desktop with a screen width of 1200px, then the first paragraph is 50% of 1200px.
0.5 * 1200px = 600px, therefore, the first paragraph is 600px wide. Using this formula, we can deduce that the second paragraph is 360px wide, and the third paragraph is 120px wide.
Check out this visual representation, in which each element has a differently colored border:
Three boxes that illustrate the percentage CSS unit.
Percentage CSS units work the same way with margins, paddings, heights, and so on.

### Viewport Width
A viewport is the visible part of a webpage. The size of a viewport varies based on the type of device being used. Hence, the viewport is 100% as wide as the visible part of the webpage. In order to calculate the width of an element, you should understand that 1vw is equivalent to 1% of the viewport’s width.
Let’s return to our paragraphs from earlier and give them widths in vws.

```css
#first{
 background-color: red;
 Width:50vw; 
 font-weight: bold;
 color:white;
}
#second{
 background-color: green;
 width:80vw;
 font-weight: bold;
 color:white;
}
#third{
 background-color:darkorange;
 color:teal;
 width:5vw;
 font-weight: bold;
}
```
Since 1vw = 1% of the viewport width, 100vw = 100% of the viewport width. Let’s take a look at our paragraphs and how they’ve scaled based on their parameters.
Three boxes that illustrate the viewport width unit.
### Viewport Height
Just like the viewport width, the viewport height refers to the height of the visible window on device. 1vh is equivalent to 1% of the viewport height.
So, if an element is set to 50vh, in the browser, that element is 50% (half) of the viewport height. The red element in the image below is 50vh high.
A red box that takes up half of the viewport height.

# Recommended Use Cases for CSS Units
It can be confusing to figure out which CSS units to use in a given scenario. It takes practice to completely understand the use cases for each unit, but I’ll highlight a few common ones below.
- ### Use pixels
  when working with properties aren’t really affected by responsiveness, like border-radius, box shadow, or border-width.
  
- ### rem
  When setting font sizes, use rem. Because it points to the root element, make sure that the font size of your root element is either 16px or 10px. (10px might make it easier to calculate rem values!)


- ### em
  When working with margins and paddings, use em units. Because the font size is related to the parent element, and every other property will adjust according to that particular element’s font size, everything can be adjusted at once.
  
- ### %
  Use percentages when working with widths and heights .

- ### vh & vw
  Use vh and vw when working with elements that depend on the viewport of the website.
