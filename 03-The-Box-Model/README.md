# 3. The Box Model

For the browser every single element inside is a "box"

## Inline, block and display

This is related to how elements occupy space.

There are 2 types of HTML elements:
- **inline**: They take up to the same space as their content. They are displayed in a line form, from left to right. Elements will wrap to the next line only if they can no fit on the same line.  
There are HTML elements which are defined as `inline` by default (`<a>`, `<strong>`, `<span>`)
- **Block**: They have the same height as the content but the same width as the container even if the content is not enough. They will always start a new line and stack on top of each other. Elements defined as `block-level` by default (`<p>`, `<h1>`, `<section>`).

The `display` property can use to change the behavior of the elements.  
We can defined the as `block`, `inline` or `inline-block`

On elements which are defined as `inline` by default, changing the `height` or `width` will have no effect. This is why we need to use the `display` property to be able to modify those elements.

### inline-block

This will apply characteristics of both properties. We will be able to control the width and height but if the element next to it can still fit on the same line it will be displayed side by side.

```HTML
<div>Block-level element</div>
<div>Block-level element</div>
<span>Inline element</span>
<span>Inline element</span>
```

```CSS
div {
  background: red; 
  height: 50px; 
  width: 300px;
  display: inline-block;
}
span {
  background: lightblue;
  height: 50px; 
  width: 300px;
  display: inline-block;
}
```

## The Box Model properties

It describe the rectangular boxes that are generated for each HTML element.  
Each Box consist of 4 parts:
+ Content - Actual content included inside the HTML
+ Padding - Space between the border and the content
+ Border
+ Margin - Space outside the border

All of them together determine the total area of each element.

There are CSS Box 5 properties:
1. Height
2. Width
3. Padding
4. Border
5. Margin

### Box units

For Box properties the percentage and length units are used.

```CSS
.container{
    width: 1000px;
}
.inside-container{
    width: 50%; /*This will be 500px*/
}
```

## Padding and Margin

We define them either by describing each side or with a shorter version which will take values in a clockwise order (top, right, bottom, left):

```CSS
.div-1{
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 50px;
  margin-left: 30px;
}
.div-2{
  margin: 10px 20px 50px 30px;
}
/* We can even use another shortcut: */
.div-3{
  margin: 10px 50px; /*top/bottom, left/right: */
}
```

### Margin collapsing

This behavior happens when 2 margins collide with each other. If we want to eliminate the margin of an element in relation to the following one, we need to make sure that both colliding elements have margin of 0 in the same side.   
Example, we want to eliminate the bottom-margin of an element, we need to make sure that the top-margin of the following is also zero. If we only eliminate the margin on one element it will look like nothing changed.

### Margin on inline elements

By default if we apply margin on inline elements such as `span`, `a`, etc. The margin will be only applied to the left and right sides of the element. If we want to apply margin for the top and bottom sides, we need to change the display property of those elements to `inline-block`

> For `in-line` elements there is also an extra space created by the breaking point. This can be eliminated by allocating both elements on the same HTML line.

We can use negative numbers for declaring margin but not for paddings.
## Border

We need to declare width, style and colour. If we use the shorthand order does not matter:
```CSS
.div-1{
  border-width: 2px;
  border-style: solid;
  border-color: red;
}
.div-2{
  border: 2px red solid;
}
```
