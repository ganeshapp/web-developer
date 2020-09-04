# CSS Notes

Cascading Style Sheets (CSS) tell the browser how to display the text and other content that you write in HTML.

>Note that CSS is case-sensitive so be careful with your capitalization.

CSS has been adopted by all major browsers and allows you to control:

* color
* fonts
* positioning
* spacing
* sizing
* decorations
* transitions

There are three main ways to apply CSS styling:

1. You can apply inline styles directly to HTML elements with the style attribute.
1. Alternatively, you can place CSS rules within style tags in an HTML document.
1. Finally, you can write CSS rules in an external style sheet, then reference that file in the HTML document.

Even though the first two options have their use cases, most developers prefer external style sheets because they keep the styles separate from the HTML elements. This improves the readability and reusability of your code.

The idea behind CSS is that you can use a selector to target an HTML element in the DOM (Document Object Model) and then apply a variety of attributes to that element to change the way it is displayed on the page.

## Change the Color of Text

We can do this by changing the style inline for an element. The property that is responsible for the color of an element's text is the color style property.

Here's how you would set your h2 element's text color to blue:

```html
<h2 style="color: blue;">Text</h2>
```

>Note that it is a good practice to end inline style declarations with a ; .

## Use CSS Selectors to Style Elements

With CSS, there are hundreds of CSS properties that you can use to change the way an element looks on your page. At the top of your code. Inside that style block, you can create a CSS selector for all h2 elements. For example, if you wanted all h2 elements to be red, you would add a style rule that looks like this:

```html
<style>
  h2 {
    color: red;
  }
</style>
```

>Note that it's important to have both opening and closing curly braces ({ and }) around each element's style rule(s). You also need to make sure that your element's style definition is between the opening and closing style tags. Finally, be sure to add a semicolon to the end of each of your element's style rules.

## Use a CSS Class to Style an Element

Classes are reusable styles that can be added to HTML elements.

```html
<style>
  .blue-text {
    color: blue;
  }
</style>
```

You can see that we've created a CSS class called blue-text within the ```<style>``` tag. You can apply a class to an HTML element like this: ```<h2 class="blue-text">Text</h2>``` Note that in your CSS style element, class names start with a period. In your HTML elements' class attribute, the class name does not include the period.

## Font CSS

```css
h1 {
  font-size: 30px;
  font-family: sans-serif;
}
```

## Import a Google Font

[Google Fonts](https://fonts.google.com/) is a free library of web fonts that you can use in your CSS by referencing the font's URL

```
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
```

Now you can use the Lobster font in your CSS by using Lobster as the FAMILY_NAME as in the following example:
font-family: FAMILY_NAME, GENERIC_NAME;

>The GENERIC_NAME is optional, and is a fallback font in case the other specified font is not available. Family names are case-sensitive and need to be wrapped in quotes if there is a space in the name. For example, you need quotes to use the "Open Sans" font, but not to use the Lobster font.

## Size Your Images

```
<style>
  .larger-image {
    width: 500px;
  }
</style>
```

## Add Borders Around Your Elements

```
<style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
  }
</style>
```

Add Rounded Corners with border-radius

```
.thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 10px;
  }
```

In addition to pixels, you can also specify the border-radius using a percentage.

### Make Circular Images with a border-radius

```
.thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }
```

## Give a Background Color to a div Element

```
.green-background {
  background-color: green;
}
```

## Set the id of an Element

In addition to classes, each HTML element can also have an id attribute.

There are several benefits to using id attributes: You can use an id to style a single element and later you'll learn that you can use them to select and modify specific elements with JavaScript.

>id attributes should be unique. Browsers won't enforce this, but it is a widely agreed upon best practice. So please don't give more than one element the same id attribute.

```
<h2 id="cat-photo-app">
```

### Use an id Attribute to Style an Element

One cool thing about id attributes is that, like classes, you can style them using CSS.

>However, an id is not reusable and should only be applied to one element. An id also has a higher specificity (importance) than a class so if both are applied to the same element and have conflicting styles, the styles of the id will be applied.

```
#cat-photo-element {
  background-color: green;
}
```

>Note that inside your style element, you always reference classes by putting a . in front of their names. You always reference ids by putting a # in front of their names.

## Adjust the Padding of an Element

All HTML elements are essentially little rectangles.

Three important properties control the space that surrounds each HTML element: padding, margin, and border.

An element's padding controls the amount of space between the element's content and its border.

```
<style>
  .injected-text {
    margin-bottom: -25px;
    text-align: center;
  }

  .box {
    border-style: solid;
    border-color: black;
    border-width: 5px;
    text-align: center;
  }

  .yellow-box {
    background-color: yellow;
    padding: 10px;
  }

  .red-box {
    background-color: crimson;
    color: #fff;
    padding: 20px;
  }

  .blue-box {
    background-color: blue;
    color: #fff;
    padding: 20px;
  }
</style>
<h5 class="injected-text">margin</h5>

<div class="box yellow-box">
  <h5 class="box red-box">padding</h5>
  <h5 class="box blue-box">padding</h5>
</div>
```

### Add Different Padding to Each Side of an Element

Sometimes you will want to customize an element so that it has different amounts of padding on each of its sides.

CSS allows you to control the padding of all four individual sides of an element with the padding-top, padding-right, padding-bottom, and padding-left properties.

```
  .blue-box {
    background-color: blue;
    color: #fff;
    padding-top: 40px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 40px;
  }

```

### Use Clockwise Notation to Specify the Padding of an Element

Instead of specifying an element's padding-top, padding-right, padding-bottom, and padding-left properties individually, you can specify them all in one line, like this:

padding: 10px 20px 10px 20px;

These four values work like a clock: top, right, bottom, left, and will produce the exact same result as using the side-specific padding instructions.

## Adjust the Margin of an Element

An element's margin controls the amount of space between an element's border and surrounding elements.

```
<style>
  .injected-text {
    margin-bottom: -25px;
    text-align: center;
  }

  .box {
    border-style: solid;
    border-color: black;
    border-width: 5px;
    text-align: center;
  }

  .yellow-box {
    background-color: yellow;
    padding: 10px;
  }

  .red-box {
    background-color: crimson;
    color: #fff;
    padding: 20px;
    margin: 20px;
  }

  .blue-box {
    background-color: blue;
    color: #fff;
    padding: 20px;
    margin: 20px;
  }
</style>
<h5 class="injected-text">margin</h5>

<div class="box yellow-box">
  <h5 class="box red-box">padding</h5>
  <h5 class="box blue-box">padding</h5>
</div>
```

>**Add a Negative Margin to an Element**: An element's margin controls the amount of space between an element's border and surrounding elements. If you set an element's margin to a negative value, the element will grow larger.

### Add Different Margins to Each Side of an Element

Sometimes you will want to customize an element so that it has a different margin on each of its sides.

CSS allows you to control the margin of all four individual sides of an element with the margin-top, margin-right, margin-bottom, and margin-left properties.

```
.red-box {
    background-color: crimson;
    color: #fff;
    margin-top: 40px;
    margin-right: 20px;
    margin-bottom: 20px;
    margin-left: 40px;
  }
```

### Use Clockwise Notation to Specify the Margin of an Element

Instead of specifying an element's margin-top, margin-right, margin-bottom, and margin-left properties individually, you can specify them all in one line, like this:

margin: 10px 20px 10px 20px;

These four values work like a clock: top, right, bottom, left, and will produce the exact same result as using the side-specific margin instructions.


