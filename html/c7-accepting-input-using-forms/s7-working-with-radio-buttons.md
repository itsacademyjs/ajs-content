When your form requires a field that have to be one from a pre-defined collection of items, then using a radio button is recommended. Radio buttons use a similar notation to check boxes, which you will learn about in the next section, the only difference being that radio button have only one option that may be chosen among many. 

This is an especially good option for choices that don't make sense when selected together. In this sense, radio buttons are like pull-down menus that allow only one choice. 

Functionally, pull-down menus and radio buttons have almost identical usage, the only difference being in a radio button group, all the options are visible to the user at once whereas in the pull-down construct, the user has to open the menu and scroll to see all the options.

Creating a radio button is very easy. All you need to do is use the `input` tag and set the type to `radio`. While using radio button, remember that setting the name attribute is very important, because the name attribute groups together controls that share the radio functionality. 

The radio functionality says that when an item is selected, it deselects the previously pressed item. If the names are not the same, the radio group will not work. 

Be careful when naming radio fields. Although you should set the name attribute the same for all buttons in a group, radio buttons must not have the same id attribute. This is because the value of the radio button is sometimes derived from it's `id` attribute. In short, radio groups need the same name attribute value, but different id values.

When working with radio buttons, the value attribute must also be carefully considered. It is important to set each individual radio button to a different value entry. Otherwise, it will be impossible to decipher which button was selected. 

If you want an option to be preselected, then you can use the attribute called 'selected'. The occurrence of the selected attribute in an `<input>` tag will preselect the item. Only one item may be selected as a default out of a radio group. If the selected attribute does not occur, the browser typically will not display any items as selected. 


A complete example of using a radio button in a form is shown below: 

```html
<html>
    <head>
        <title>Radio Button Example</title>
    </head>
    <body>
        <h1 align="center">Radio Button Example</h1>
        <hr />
        <form action="http://www.htmlref.com/scripts/formecho.php"
        method="post" name="form1" id="form1">
            <strong>Gadget Color:</strong><br />
            Groovy Green: <input type="radio" name="Color" id="radio1" value="Green" />
            Rocket Red: <input type="radio" name="Color" id="radio2"
            value="Red" checked="checked" />
            Yipee! Yellow: <input type="radio" name="Color" id="radio3"
            value="Yellow" />
            <br />
            <input type="submit" value="Submit" />
        </form>
    </body>
</html>
```