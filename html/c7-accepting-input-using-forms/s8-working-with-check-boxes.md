If the form contains a few options to select from and the options are such that they aren't mutually exclusive, meaning the user can select one or more options, then the input of the type check box might be used.

Check boxes are best used to toggle choices on and off. Although it is possible to have multiple numbers of check boxes and let the user select as many as he or she wants, if there are too many it can be difficult to deal with because they take up so much screen real estate, so in such cases where the number of options is too high, remember to use select boxes or scroll lists.

To create a check box, use an `<input>` tag and set the type attribute equal to `checkbox`. The check box also should be named by setting the name and id attributes. Here is an example of a checkbox:

```html 
<input type="checkbox" name="Cheese" id="Cheese" />
```

In this simple example, if the check box is selected, a value of Cheese=on will be transmitted to the server. Setting a value for the check box might make sense when you don't want the default "on" and "off" values to be transmitted. Values to be transmitted instead of the default value can be set with the value attribute. Here is an example: 

```html
<input type="checkbox" name="Extras" id="Extras" value="Cheese" />
```
The above code would send a response such as Extras=Cheese to the server. 

Under traditional HTML, it was possible to have multiple check box controls with the same name. For example, look at the following HTML 4 markup

```html
Cheese: <input type="checkbox" name="Extras" id="Extras" value="Cheese">
Pickles: <input type="checkbox" name="Extras" id="Extras" value="Pickles">
```

The above markup would send multiple entries such as the following to the server when both extras were
selected:

```Extras=Cheese&Extras=Pickles```

However, under XHTML you should have unique id attributes everywhere, so you would
write the same markup differently, as shown below:

```html
Cheese: <input type="checkbox" name="Extras" id="cheese" value="Cheese" />
Pickles: <input type="checkbox" name="Extras" id="pickles" value="Pickles" />
```
There is yet another reason to avoid the same name and id on multiple checkbox apart from the one mentioned above. Some web programming environments make it difficult to parse key-value pairs where multiple keys have the same name.

Another cool feature of a check box is that, it is possible to set a check box to be selected by default by using the checked attribute within an `<input>` tag. The checked attribute requires no value under traditional HTML. However, under XHTML you have to use checked="checked" to be
perfectly correct. 

A complete example using check box fields properly is shown here:

```html
<html xmlns="http://www.w3.org/1999/xhtml" lang="en">
<head>
<title>Checkbox Example</title>
<meta http-equiv="content-type" content="text/html; charset=ISO-8859-1" />
</head>
<body>
<h1 align="center">Checkbox Example</h1>
<hr />
<form action="http://www.htmlref.com/scripts/formecho.php"
method="post" name="form1" id="form1">
<strong>Gadget Bonus Options:</strong><br />
Super-magneto:
<input type="checkbox" name="mag" id="mag" value="Magnetize" /><br />
Kryptonite Coating:
<input type="checkbox" name="krypto" id="krypto"
value="Anti-Superman" checked="checked" /><br />
Anti-gravity:
<input type="checkbox" name="antigrav" id="antigrav"
value="Anti-gravity" /><br />
<input type="submit" value="Submit" />
</form>
</body>
</html>
```