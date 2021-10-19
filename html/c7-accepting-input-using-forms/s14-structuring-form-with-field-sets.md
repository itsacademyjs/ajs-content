Often, if your form is very large, you can group form fields together using the `fieldset` HTML tag as shown in the example below:

```html
<form action="/action_page.php">
  <fieldset>
    <legend>Personalia:</legend>
    <label for="fname">First name:</label>
    <input type="text" id="fname" name="fname"><br><br>
    <label for="lname">Last name:</label>
    <input type="text" id="lname" name="lname"><br><br>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email"><br><br>
    <label for="birthday">Birthday:</label>
    <input type="date" id="birthday" name="birthday"><br><br>
    <input type="submit" value="Submit">
  </fieldset>
</form>
```

You can further organize your code by using fieldsets outside your forms even though they will still be part of the same forms. This can be acheived using the "form" attribute.

```html
<form action="/action_page.php" method="get" id="form1">
  <label for="favcolor">What is your favorite color?</label>
  <input type="text" id="favcolor" name="favcolor">
  <input type="submit">
</form>

<fieldset form="form1">
  <legend>Personalia:</legend>
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" form="form1"><br><br>
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" form="form1">
</fieldset>
```

Generally fieldsets are used to make semantically meaningful groups of a large set of form fields. Wrapping fields using a fieldset usually draws a box around the fields. Apart from the `form` attribute, fieldset also takes the `name` attribute, indicating the name of the field set, for accessibility reasons. It also takes another attribute called `disabled`. If an occurrence of this attribute is found in the opening tag,then all the input form fields within the fieldset are automatically disabled. 