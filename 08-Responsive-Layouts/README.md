# Fluid and Responsive Layouts

Responsive web design refers to the idea of creating layouts which adjust to the way they are displayed and the type of media that renders them. [Article](https://alistapart.com/article/responsive-web-design/)

Responsive web design is not a CSS feature but rather is the thought process on using CSS to creating optimal view experiences on any device.

There are 3 main components when creating a responsive web design:
1. Fluid Layout
2. Flexible Images
3. Media Queries

## Fluid Layouts

This refers to using relative units rather than absolute (fix). We can change px into percentages or rems.

We could also determine a `max-width` and `width`. This will apply the max-width to every device which has a screen bigger than the specified value (usually on px) and the min-width can be relative (some percentage).

## Flexible images

It is the idea of defining how a displayed image should look on different screen sizes. We know that not everything will look the same over different sizes but we need to disclose how it should look like. 

Probably some images will change their position and will display something different. If we want some part of the image to be always displayed we need to use the `background-size` and `background-position` properties.

## Media queries

They are initiated by using the `@media` rule then specify the **media type** and the **media feature**:

```CSS
@media screen and (max-width: 1000px){
    h1{
        font-size: 16px;
    }
}
```

Currently we can use 4 different **media types** for media queries:
- all: matches all devices.
- print: matches print-related displays. How the layout will look like if the user needs to print it out.
- speech: matches the screen reading devices.
- screen: matches all other devices which aren't categorize as print or speech.

**Media features** are used to test an specific feature of the device:   
- `@media (width: 500px) {...}`
- `@media (orientation: landscape) {...}`

We need to use the keyword `and` to combine **media features** with **media types** or with multiple **media features**

- `@media screen and (width: 500px) {...}`
- `@media (orientation: landscape) and (min-width: 300px) {...}`

It is convention to add all media queries at the button.

When using `width` as the feature it is important to use a range, if we only use a single value that media query will be applied only when the width equals that value, if there is an additional or missing pixel the query will no longer apply.

## Common breakpoints

- 320px: Mobile portrait
- 480px: Mobile landscape
- 600px: Small tablet
- 768px: Tablet portrait
- 940 - 1024px: Tablet landscape
- 1280px and greater: desktop, laptop

Despite this breakpoints the best practice is to adjust our web design only on the device that needs adjustment, not to every screen type.

## What to design first

There are two ways of planning the responsive design:

1. Desktop first - Will create the design for desktop at the beginning and then make changes for the other screen types. Media queries will probably include the `max-width` feature.
2. Mobile first - It will be the other way around. creating design for mobile screens and then adjusting for bigger screens. Uses the `min-width` feature.

## Tools to test responsive websites

- [BrowserStack](https://www.browserstack.com/)
- Developer tools of each browser
