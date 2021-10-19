# LinkedIn-CSS-Course
## Tips and useful links:

- [CSS - Mozilla documentation](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [Code Guide for HTML and CSS](https://codeguide.co/)
- [CSS values and units (px, rem, etc)](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [Lorem Picsum](https://picsum.photos/)
- [Colours neil-orange-peel](https://colours.neilorangepeel.com/) available keyword colours.
- [Randoma11y](https://randoma11y.com/) Provides color combination with great contrast for colorblind people.
- [Coolors.co/app](https://coolors.co/861388-e15a97-eeabc4-c799a6-4b2840) To generate combinations and pallets.

## Selectors, classes and ids

### Selectors

- Universal selector: It is applied by using an asterisk `*`. It will be applied to all elements inside the DOM.

- Type selectors: They match the selection according to the type of element.

```CSS
/* Universal Selector*/
* {
    padding: 10px;
}
/* Type selector*/
h1 {
    colour: red;
}
```

### Classes

It requires to include the class on the html element and also to define it on the CSS file.

Classes start with a dot `.` on the CSS file

They are reusable for many HTML elements.

```HTML
<p class="red-paragraph">This is a paragraph.</p>

<style>
    .red-paragraph {
        colour: red;
    }
</style>

```
