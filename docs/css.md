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
```
<h2 style="color: blue;">Text</h2>
```
>Note that it is a good practice to end inline style declarations with a ; .

## Use CSS Selectors to Style Elements

With CSS, there are hundreds of CSS properties that you can use to change the way an element looks on your page. At the top of your code. Inside that style block, you can create a CSS selector for all h2 elements. For example, if you wanted all h2 elements to be red, you would add a style rule that looks like this:

```
<style>
  h2 {
    color: red;
  }
</style>
```

>Note that it's important to have both opening and closing curly braces ({ and }) around each element's style rule(s). You also need to make sure that your element's style definition is between the opening and closing style tags. Finally, be sure to add a semicolon to the end of each of your element's style rules.

## Use a CSS Class to Style an Element

Classes are reusable styles that can be added to HTML elements. 
```
<style>
  .blue-text {
    color: blue;
  }
</style>
```
You can see that we've created a CSS class called blue-text within the ```<style>``` tag. You can apply a class to an HTML element like this: ```<h2 class="blue-text">Text</h2>``` Note that in your CSS style element, class names start with a period. In your HTML elements' class attribute, the class name does not include the period.

## Font CSS
 
```
h1 {
  font-size: 30px;
  font-family: sans-serif;
}
```

## Import a Google Font








