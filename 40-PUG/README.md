# PUG HTML 

Full documentation [here](https://pugjs.org/api/getting-started.html).

## Starting project

To install the pug command line interface with npm:   
Run `npm install pug-cli -g`

To watch for the index file tun the command:

`pug -w ./ -o ./html -P`

`-w` will watch for the any file inside the directory specified after (in this case the root directory `./`)

`-o` will specify where we want the output to be located (in this case the "html" folder `./html`)

`-P` make the code "pretty" includes indentation and stuff.

## Documents types

We can use different type of documents (full information in documentation) such as:

- html
- xml
- strict

## Basics

- Indentation will determine parent - child elements.
- `#` is used to declare CSS IDs
- `.` is used to declare CSS classes
- If we do not specify an element but only a class or ID pug will create a `div` element by default.
- Attributes will be declared inside parenthesis like a normal HTML attribute:

```PUG
input#input-ID.input-class(type="password", name="passwordInput")
```

We can include JavaScript variables by adding a `-` dash before its declaration. It is a common practice to include a "variables" section at the beginning of the document.

```PUG
block variables
	- var title = "New website"
	- const fontcolor = "#333333"
	- var myClasses = [ "class1", "class2", "class3"]

div(class=myClasses)  
```

## Styles declaration using JavaScript Syntax

We can include a JavaScript object that holds all styles which are needed, then we call those styles as an attribute:

```PUG
block variables
	- var myStyles = {
        "color": "red",
        "background-color": "blue",
        "font-size": "14px"
    }

div(style=myStyles)
```

## Attributes declaration using JavaScript Syntax

Similar to the previous example with the difference that we need to use `&attributes` to implement those attributes:

```PUG
block variables
	- var myAttributes = {
        "src": "myPhoto.png",
        "alt": "New Photo"
    }

img&attributes(myAttributes)
```

## CSS and JS

We can include CSS or JS file by adding `link` for CSS and `script` for JS:

```PUG
doctype html
html
	head
		link(href="vendor.css", rel="stylesheet", type="text/css")
	    link(href="styles.css", rel="stylesheet", type="text/css")
	body
    	div#app
			block app
        script(src="vendor.js")
	    script(src="script.js")
```

## For Each loop

`each` and `for` are the same loop but have different name.

We can go through an array or object and display each element. Additionally we can include an `else` statement at the end in case there is no elements to display.

```PUG
doctype html
html
    - var numbers = [3,435,546,883,164]
    - var ppl = {"John": 86, "Paul": 24}
	head
	body
        h1 Each Loop
        each n,i in numbers
            p= "index: "+ i +"- number: "+ n
        else
            p No values found 
        //- Object syntax
        each value,index in ppl
            p= "Name: "+ index +" , age: "+ value
        else
            p No values found 
```

## Conditionals (If-Else statement)

```PUG
doctype html
html
    - var user = {name: "Ernesto", loggedIn: false, lastLogin: 6}
	head
	body
        h1 Conditionals
        if user.loggedIn
            p 
                | Welcome back, 
                strong #{ user.name }
        else if user.lastLogin < 10
            p Your last login was #{ user.lastLogin } minutes ago
            p
                a(href="#") Log In again
        else 
            a(href="#") Log in
```

## Inserting JavaScript values into HTML elements

We have two ways to insert values from a JavaScript Object into the HTML content:

1. Using `#{ object.property}`. This option is very useful when we want to include more text besides the value of the property
2. Using `= object.property` it is more convenient when we only want to use the object value.

```PUG
doctype html
html
    - var user = {name: "Ernesto", loggedIn: false, lastLogin: 6}
	head
	body
        h1 Conditionals
        if user.loggedIn
            p 
                | Welcome back, 
                strong= user.name //- Case number 2
        else if user.lastLogin < 10
                //-Using case 1
            p Your last login was #{ user.lastLogin } minutes ago 
            p
                a(href="#") Log In again
        else 
            a(href="#") Log in
```

## Case Statement

```PUG
doctype html
html
    - var orderStatus = 'Pending'
	head
	body
        h1 Case Statement
        case orderStatus
            when 'Pending'
                //- Do something
            when 'In_Transit'
                //- Do something else
            when 'Completed'
                //- DO another stuff
            default
                //- Will be used when none of the above where true 
```

## `include` keyword

It is used to include multiple HTML files. This way we can split components into different files. If we need to update a component we only need to do it in one of the files. We usually have components which will be repeated multiple times into the application such as navigation bars, footers, heroes, etc. 

```PUG
//- index.pug
doctype html
html
    head 
    body 
        include components/nav.pug

//- about.pug
doctype html
html
    head 
    body 
        include components/nav.pug
        h3 About us

//- nav.pug --->PATH(components/nav.pug)
h1 New Application 
nav
    a(href="index.html") Home
    a(href="about.html") About us
    a(href="#") Contact us
```

## Mixins

With mixins we can pass parameters which will change the structure of the output element.   
They work similar to the `include` structure but with the difference that we pass information into them:

```PUG
//- mixin comment
mixin comment(commentData)
    .comment
        .date= commentData.date
        .author= commentData.author
        .text= commentData.text

//- index.pug
doctype html
html
    - var c = { date: '10-06-2022', author: 'Jay', text: 'You are great!'}
    head 
    body 
        h1 Mixins app
        +comment(c)
```


## Template Inheritance: Extends and Block

Pug supports template inheritance. Template inheritance works via the `block` and `extends` keywords.

In a template, a `block` is simply a “block” of Pug that a child template may replace. This process is recursive.

Pug blocks can provide default content, if appropriate. Providing default content is purely optional, though. 

```PUG
//- layout.pug
html
  head
    title My Site - #{title}
    block scripts
      script(src='/jquery.js')
  body
    block content
    block foot
      #footer
        p some footer content
```

To extend this layout, create a new file and use the `extends` directive with a path to the parent template. Then, define one or more blocks to override the parent block content.

```PUG
//- page-a.pug
extends layout.pug

block scripts
  script(src='/jquery.js')
  script(src='/pets.js')

block content
  h1= title
  - var pets = ['cat', 'dog']
  each petName in pets
    include pet.pug

//- pet.pug
p= petName    
```