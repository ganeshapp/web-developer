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

## Checkboxes

Checkboxes are a type of input.

Each of your checkboxes can be nested within its own label element. By wrapping an input element inside of a label element it will automatically associate the checkbox input with the label element surrounding it.

All related checkbox inputs should have the same name attribute.

It is considered best practice to explicitly define the relationship between a checkbox input and its corresponding label by setting the for attribute on the label element to match the id attribute of the associated input element.

Here's an example of a checkbox:

```
<label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
```

## Use the value attribute with Radio Buttons and Checkboxes

When a form gets submitted, the data is sent to the server and includes entries for the options selected. Inputs of type radio and checkbox report their values from the value attribute.

For example:

```
<label for="indoor"> 
  <input id="indoor" value="indoor" type="radio" name="indoor-outdoor">Indoor 
</label>
<label for="outdoor"> 
  <input id="outdoor" value="outdoor" type="radio" name="indoor-outdoor">Outdoor 
</label>
```

Here, you have two radio inputs. When the user submits the form with the indoor option selected, the form data will include the line: indoor-outdoor=indoor. This is from the name and value attributes of the "indoor" input.

If you omit the value attribute, the submitted form data uses the default value, which is on. In this scenario, if the user clicked the "indoor" option and submitted the form, the resulting form data would be indoor-outdoor=on, which is not useful. So the value attribute needs to be set to something to identify the option.

```
<label><input type="radio" name="indoor-outdoor" value="Indoor"> Indoor</label>
<label><input type="radio" name="indoor-outdoor" value="Outdoor"> Outdoor</label><br>
<label><input type="checkbox" name="personality" value="Loving"> Loving</label>
<label><input type="checkbox" name="personality" value="Lazy"> Lazy</label>
<label><input type="checkbox" name="personality" value="Energetic"> Energetic</label>
```

## Check Radio Buttons and Checkboxes by Default

You can set a checkbox or radio button to be checked by default using the checked attribute.

To do this, just add the word "checked" to the inside of an input element. For example:

```
<input type="radio" name="test-name" checked>
```

## Basic Structure

```
<!DOCTYPE html>
<html>
  <head>
    <!-- metadata elements -->
  </head>
  <body>
    <!-- page contents -->
  </body>
</html>
```


