# 4 Typography

## font-weight

This property determines how bold will the text going to be. It takes a number between 100 to 900 going 100 by 100. (100, 200, 300, so on)

## Web fonts

It expands font options, these files can be downloaded similarly to images.   
They are added with the `@font-face` keyword.
1. It should be declared on the stylesheet.
2. `font-family` keyword will be used to describe the font family of the font, we can assign any name but it is convention to give the same name as the type face.
3. `src` indicated where to get the file from. the path can be absolute or relative.

```CSS
@font-face {
    font-family: "My font";
    src: url(../fonts/my-font.woff)
}
```

We can also download the fonts on the HTML file.   
We need to include the link of the font right before the CSS file using that font. This would only require to use the same name on the `font-family` property as the one declared on the downloaded file.

```HTML
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto+Condensed:ital,wght@0,300;1,300&display=swap" rel="stylesheet">
<link rel="stylesheet" href="/styles.css">
```

```CSS
div {
    font-family: 'Roboto', sans-serif;
}
```

## Font size

- 1em = inherit font size.  
If not unit can be inherited then the default from the browser will be applied.

- 1rem - root "em"  
It is relative to the root HTML element

Using these relative units will allow us to change the size for multiple elements (for different screen sizes) by only changing one element's size, other elements will inherit this change.

## font shorthand

It is short for 6 properties:
- font-style
- font-size
- font-weight
- font-family
- font-variant
- line-height

It should always include values for the `font-size` and `font-family`, others are optional.

Order matters!:
- `font-style`, `font-variant` and `font-weight` should be declared before `font-size`.
- `font-variant` small caps only
- `font-size`/`line-height`
- `font-family` must be the last value.

```CSS
div {
    font: italic small-caps bold 24px/1.5 Helvetica, sans-serif;
}
```

## text-decoration

It is the shorthand of the following properties:
- `text-decoration-line (underline)`
- `text-decoration-color (red)`
- `text-decoration-style (solid)`

`text-align` used to align content withing a block element, add it to the element itself or the parent element. This works only to block elements, not in-line elements.

## Useful links

- [CSS Font Stack](https://www.cssfontstack.com/)
- [Google fonts](https://fonts.google.com/)