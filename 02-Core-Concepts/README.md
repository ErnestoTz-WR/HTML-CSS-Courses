# 2. Core concepts

## CSS Specifications and W3 publishing documentation process

Code labeled as:

- **Recommendation** is good to go
- **Candidate Recommendation or Proposed Recommendation**: still waiting for feedback and approval. It is okay to be implemented but it might have some updates or working progress.
- **Superseded Recommendation**: aspect that has been replaced.
- **Draft stages** still experimental and are not supported by all browsers.

## CSS Values and Units

**Length** can be defined on CSS by two types of units:

- Absolute: Fixed units, always the same size. No affected by values in related elements. Example: px, cm, mm, pt.
```CSS
    h1{
        padding: 10px 20px 10px 20px;
    }
```

- Relative: Relational sizing, not fixed. Dependent upon values declared in parent and ancestor elements. Example: em, rem, vw, vh.

```CSS
    h1{
        padding: 1.2rem 2.3rem 1.2rem 2.3rem;
    }
```

## Colours 

### RGB

`rgb()` this indicates rgb as a function it expects integer parameters between 0-255 or 0% - 100%.

`rgba()` - term used for red green blue alpha, where alpha indicated the opacity as a percentage.

```CSS
rgb(55,34,40) /*No alpha channel*/
rgba(55,34,40,0.5) /*50% opacity*/
rgba(55,34,40,1) /*100% opacity*/
```

### HSL

Defines colours by their hue, saturation and lightness 

## Class and IDs

### Class

We define the name, they can be used more than once. They are declared on the CSS file starting with a `.`

We can apply more than one class to HTML elements.

```CSS
.fancy{
    display: block;
    background-color: red;
    padding: 10px;
}
.intro{ /* attributes */}
```

```HTML
<div class="intro"></div>
<div class="intro fancy"></div>
```

We can even specify styles only if the HTML element has 2 classes included:

```CSS
.intro.fancy{
    /* This code will be only render if .fancy AND .intro are included. */
}
```

### ID

We also define the name, they can not be used more than once. They are declared starting with a `#` on the CSS file.

They can be used for in-page linking. If we use the id as the `href` of a link, this will make the page go to the element with that ID.

```CSS
#article-area{
    /* Attributes */
}
```

```HTML
<a href="#article-area"> Link to the article. </a>
<section>All the Article</section>
```

## Descendant Selectors

The relationship between nested elements inside the HTML file can also give us an specific selection.

To identify this relationship we leave an space between selectors on the CSS file:

```HTML
<section>
    <p> Some text
</section>
```

```CSS
section p {
    /* Attributes for every p inside the section*/
}
```

> The rule to follow here is that we declare the general styles, but only if we need to be specific for an element we would use descendant or combined classes

## Grouping Selectors

We can apply the same stiles to more than one selector on the CSS file by separating them with a comma `,`

```CSS
h1, h2, .header-article{
    /* Styles for H1, H2 and the class */
}

/* We can also apply Descendant selectors here */

section p, .article h1{
    /* Styles for p inside the section and the H1 inside the article class*/
}

```

## Inheritance and Specificity

### Inheritance

Nested elements will inherit styles from the parent elements, however we can override them by being specific.  
There are some styles which are not inherited. W3 has a list of all them. 

### Specificity

It determines how browsers decide which CSS rule takes precedence:

1.  Universal (*)
2.  Type (p)
3.  Class (.example)
4.  id (#example)

```CSS
section {
  font-family: sans-serif;
  font-size: 30px;
  color: orange;
}
* {
  color: lightblue;
}
p {
  color: green;
}
.example {
  color: black;
}
#example {
  color: purple;
}
/* Descendant Selector*/
section p {
  color: lightgreen;
}

```

Descendant Selectors will not override styles coming from IDs or classes. I will only override styles coming from Type or the Universal.

### Useful tools

There are some tools which can help use to determine how the browser will calculate the importance of our styles.

[Specificity-Keegan](https://specificity.keegan.st/)

## Cascade

Styles Sheets are read from top to bottom.  
This means that in the case that there are declarations applied to the same element and with the same specificity value the style which was loaded last will take precedence.

This also applies to declarations written on the same block.

```CSS
p {
    font-size: 12px;
}
/* This styles will be applied*/
p {
    font-size: 12px;
}

h1 {
    colour: red; /* won't be applied*/
    colour: green; /* will be applied*/
}
```

## `!important` keyword 

It will override styles even when their Specificity value is higher.  
> Since it does not follow any rules it is in general considered a bad practice.

## Pseudo-classes

They are combined with other selectors.  
They will refer to events happening on the HTML element. Some examples are the ones use on links (`:link`, `:visited`, `:hover`, `:active`, `:focus`, etc)

```CSS
body {
  font-size: 20px;
}
a {
  color: red;
}
a:link {
  color: green;
}
a:visited {
  color: gray;
}
a:focus {
  outline: 1px solid black;
}
```