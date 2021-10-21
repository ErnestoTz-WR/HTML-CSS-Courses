# 3. The Box Model

For the browser every single element inside is a "box"

## Inline, block and display

This is related about how elements occupy space.

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

All of the together determine the total area of each element.

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