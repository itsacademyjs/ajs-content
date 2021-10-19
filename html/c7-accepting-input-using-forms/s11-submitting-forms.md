Once a form has been filled in, there must be a way to send it on its way, whether it is submitted to a program for processing or simply mailed to an e-mail address. For such reasons, the input element has two values for the type attribute for accomplishing this. These two values are 'submit' and 'reset'.

Setting the type attribute for an `<input>` tag to reset creates a button that allows the user to clear or set to default all the form fields at once. Setting the type attribute for `<input>` to submit creates a button that triggers the browser to send the contents of the form to the address specified in the action attribute of the enclosing form element. We have already discussed about the action attribute in the previous sections.

```html
<html>
<head>
<title>Reset and Submit Example</title>
<meta http-equiv="content-type" content="text/html; charset=ISO-8859-1" />
</head>
<body>
<h1 align="center">Gadget Order Form</h1>
<hr />
<form action="http://www.htmlref.com/scripts/formecho.php"
method="post" name="form1" id="form1">
<strong>Customer Name:</strong>
<input type="text" name="UserName" id="UserName" size="25"
maxlength="35" />
<br />
<strong>Password:</strong>
<input type="password" name="Pass" id="Pass" size="10" maxlength="10" />
<br />
<strong>Gadget Type:</strong>
<select name="GadgetType" id="GadgetType">
<option value="SG-01">Super Gadget</option>
<option value="MEG-G5">Mega Gadget</option>
<option value="MO-45">Mongo Gadget</option>
<option selected="selected">Gadget</option>
</select>
<br /><br />
<input type="submit" value="Order Gadget" />
<input type="reset" value="Reset Form" />
</form>
</body>
</html>
```

Because the Submit and Reset buttons cause an action, either form submission or field reset, it may not be obvious why the name field can be useful. Although having multiple Reset buttons might not be so useful, multiple Submit buttons are useful because the value of the button is sent to the address specified in the form element's action attribute.

One possible use might be to have three Submit buttons: one for add, one for delete, and one for update.

```html
<input type="submit" value="Place Order" name="Add" />
<input type="submit" value="Delete Order" name="Delete" />
<input type="submit" value="Update Order" name="Update" />
<input type="reset" value="Reset Form" name="ResetButton" />
```