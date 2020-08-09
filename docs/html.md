# HTML Notes

## Introduction to HTML5 Elements

HTML5 introduces more descriptive HTML tags. These include main, header, footer, nav, video, article, section and others.

These tags give a descriptive structure to your HTML, make your HTML easier to read, and help with Search Engine Optimization (SEO) and accessibility. The main HTML5 tag helps search engines and other developers find the main content of your page.

Example usage, a main element with two child elements nested inside it:

```
<main> 
  <h1>Hello World</h1>
  <p>Hello Paragraph</p>
</main>
```

>Note: Many of the new HTML5 tags and their benefits are covered in the Applied Accessibility section.

## Add Placeholder Text to a Text Field

Placeholder text is what is displayed in your input element before your user has inputted anything.

You can create placeholder text like so:

```
<input type="text" placeholder="this is placeholder text">
```

>Note: Remember that input elements are self-closing.

## Radio Buttons

adio buttons are a type of input.

Each of your radio buttons can be nested within its own label element. By wrapping an input element inside of a label element it will automatically associate the radio button input with the label element surrounding it.

All related radio buttons should have the same name attribute to create a radio button group. By creating a radio group, selecting any single radio button will automatically deselect the other buttons within the same group ensuring only one answer is provided by the user.

>It is considered best practice to set a for attribute on the label element, with a value that matches the value of the id attribute of the input element. This allows assistive technologies to create a linked relationship between the label and the child input element. For example:

```
<label for="indoor">
  <input id="indoor" type="radio" name="indoor-outdoor"> indoor
</label>
<label for="outdoor">
  <input id="outdoor" type="radio" name="indoor-outdoor"> outdoor
</label>
```

