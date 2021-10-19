A select box or a select menu, sometimes referred to as a pull-down menu, enables the user to select one choice out of many possible choices. One nice aspect of select menus is that all choices do not have to be seen on the screen and are generally are hidden until the user clicks on the select box and opens it.

To create a pull-down menu, you need to use the `<select>` tag. The tag should contain one or more occurrences of the option element. Each `<option>` tag specifies a menu choice when the select box is open. The following markdown illustrates the usage of the `<select>` tag with four `<option>` tags that form the four choices that the box contains: 

```html
<select name="GadgetType" id="GadgetType">
    <option>Super Gadget</option>
    <option>Mega Gadget</option>
    <option>Mongo Gadget</option>
    <option>Plain Gadget</option>
</select>
```
As you can see in the code fragment, like all form fields the select element has name and id attributes used to set a unique name for the field. It is also possible to set the size attribute on a `<select>` tag, but generally this is not set unless the menu is a scrolled list.

The option element has a few attributes as well. An occurrence of the attribute selected in an <option> tag sets the form control to select this item by default. You might recall that this is similar to other multiple choice input types we have dealt with so far, like radio button and check boxes. If there is no occurence of the selected attribute in any of the options inside a particular select tag, the browser will choose the first `<option>` within the select element as the default. 

If multiple selected attributes are specified, the result is generally to select the final <option> tag with a selected attribute. But please do not not assume this result and instead focus on developing correct markup. Having multiple occurrences of selected attribute is not correct markup. 

Generally, the value submitted when the form is sent is the value enclosed by the option element. However, it is possible to set the value attribute for the element that will be returned instead. Separating the text of the option from the submitted value is often a good idea so you can have a descriptive message for the user
and a short data item for transmission. 

A complete example of a simple pull-down menu is shown here:

```html
<html>
<head>
<title>Select Example</title>
</head>
<body>
<h1 align="center">Select Example</h1>
<hr />
<form action="http://www.htmlref.com/scripts/formecho.php" method="post" name="form1" id="form1">
<strong>Gadget Type:</strong>
<select name="GadgetType" id="GadgetType">
<option>Super Gadget</option>
<option value="MEG-G5">Mega Gadget</option>
<option value="MO-45" selected="selected">Mongo Gadget</option>
<option>Plain Gadget</option>
</select><br />
<input type="submit" value="Submit" />
</form>
</body>
</html>
```