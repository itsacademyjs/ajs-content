The password form field is identical to the text entry field, except the input to the field is not echoed back to the user when typed. This is useful in maintaining privacy and secrecy of password keys.

In many cases, the browser will render either a bullet or an asterisk or sometimes even a dot to avoid people seeing the character that they just entered. This discourages "shoulder surfing", the technique used to peek into the password that another user is entering.

To set a password form control, use the `<input>` tag again but this time set the type attribute equal to password. As with the text field, it is possible to specify the size of the field in characters with size and the maximum entry in characters with the maxlength attribute. 

In the case of the password field, unlike the normal text field, it is probably good practice to limit its length so users don't become confused about how many characters they have entered. Most large corporations have a limit to the size of the password, and it almost never exceeds 128 characters.

Another issue that makes the password field slightly different from the single-line text entry field is the default value. Setting a default value for a password field with a value attribute doesn't make much sense. This is because the user can see the default value by just viewing the HTML source of the document. Hence, it is better to not set the value attribute of a password field.

There are some similarities, of course, with the single line text entry input field. The name and id attributes must be set, as these are used to handle the password input in both the client side JavaScript scripts as well the server-side programs that perform validation, hashing, encryption, and storage.
 
A complete example of the
password field's use within the form is shown here:

```html
<html>
    <head>
        <title>Password Field Example</title>
    </head>
    <body>
        <h1 align="center">Password Field Example</h1>
        <hr />
        <form action="link" method="post" name="form1" id="form1">
            <strong>Password:</strong>
            <input type="password" name="Pass" id="Pass" size="10" maxlength="10" />
            <br />
            <input type="submit" value="Submit" />
        </form>
    </body>
</html>
```