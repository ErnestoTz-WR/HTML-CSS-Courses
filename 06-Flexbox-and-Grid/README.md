# 6 - Flexbox and Grid

In Flexbox items are align on a single axis, which means it is one-dimensional. We can arrange items by rows or columns but not both at the time.   

Grid can work with layouts with both dimensions (rows and columns) at the same time.

## Flex

- **Flex container**: parent element.
- **Flex items**: child element.

We can define a container by declaring the display property as `flex` or `inline-flex`. 

### Flex properties for size

- flex-basis: sets the initial size of the item.
- flex-grow: determines how items will expand if there is extra space in the container.
- flex-shrink: determines how items will shrink if there isn't enough space in the container.

We can define all three with the shorthand `flex`:

`flex: grow shrink basis`

`flex: 0 1 100px`

This property should be applied to the item, not to the container.

### align and justify items with flexbox

- `justify-content`: aligns items on the main axis (x)
- `align-items`: aligns items on the cross axis (y)

## Grid

It contains columns, rows and gutters.   
Gutters are the space between columns.

Similar to Flexbox, grid has containers and items. The container is declare with the `display` property as well by declaring it as `grid` or `inline-grid`.

## Explicit grid

We can create an explicit grid by declaring that on the container. We need to use the properties `grid-template-columns` and `grid-template-rows`:

```CSS
.grid-container{
    display: grid;
    grid-template-columns: 100px 100px 100px; /* 3 columns */
    grid-template-rows: 200px 200px /* 2 rows */
}
```

## The fraction unit: **fr**

**fr**: represents a fraction of the available space in the grid container.

```CSS
.grid-container{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr; /* 3 equal columns */
    grid-template-columns: 1fr 2fr 1fr; /* 2 equal columns and the medium one will take twice the space of the other 2*/
}
```

## gap property

It refers to the gutters. We can define the space between items.

`gap: 10px;` refers to rows and columns.    
`gap: 10px 20px;` will give 10px rows, 20px columns.

the `fr` unit is not accepted here.

## Implicit grid

It refers to the part of the grid we are unable to define right now but this content might arrive later on. Such as dynamic content.

We will define it using `grid-auto-columns` and `grid-auto-rows`

## Positioning grid

This property has to be applied to the items. The properties are:

- `grid-colum`: which is shorthand for `grid-column-start` and `grid-column-end`
- `grid-row`: which is shorthand for `grid-row-start` and `grid-row-end`

We specify a number value for the beginning and the end. When using the shorthand we need to use a `/` in the middle.
