# 1. Getting Started

## How reference a CSS file

There are 3 ways to link a CSS file into and html file

### 1.  Using the link tag on the html file with the proper link
```html
<head>
    <link rel="stylesheet" href="css/styles.css">
</head>
```
This way we are inserting an external file.  
The advantage of using external files is that we can use the same file on different html files.

#### 2. Using the `@import`:
```html
<head>
    <style> @import url ("css/style.css");</style>
</head>
```
The downside of using `@import` is that it can slowdown the performance. It does not allow parallel downloads, it has to finish downloading an entire stylesheet to start downloading the following one.  
However, this method is commonly used for css preprocessor such as Sass or less.

### 3. Inline method & Internal
**Inline**

```html
<p style="color:red; padding:20px">Some text</p>
```
CSS added by any other method will be overridden by this inline method.

**Internal**
```html
<head>
    <style>
        h1 {
            color: green;
        }
        h2 {
            color: blue;
        }
    </style>
</head>
```
More flexible than internal but only recommended for styles that will only be applied to one page.

## Retina

Term introduced by Apple but now widely use by other manufactures.

Retina = High pixel density.

**Pixel Density** refers to how many pixels are contained within a space, usually measured by pixels per inch, or PPI for short, and sometimes referred to as dots per inch, DPI. Retina displays have double the number of pixels per inch and can fit two pixels within the same width and height of a non-Retina display. The more pixels there are within the same area, the smaller the pixels are, which is how text and images appear smoother, clearer, and show more detail.

## Absolute and Relative paths

**Absolute** paths refer to a resource located on a server somewhere on the cloud.
*Hot-linking* is when we link to specific files such as images. This will use bandwidth from the provider. It is okay to include links but not tho embed the link for specific files.

```html
<a href="http://somelink.com"> Good link </a>
<img src="http://somelink.com/images/some-picture.jpg"> Hotlink! Not okay
```

**Relative** path is when we store files or resources locally. We can refer to this files with a simple path.  
> '`../`' means "go back one directory"