There might be cases where you need more than a single line of text input. In such cases, the input element won't be helpful. Instead, you should be using another HTML element called the `textarea` element.

Just like the input field of type text, you will notice several similar attributes. Some of the attributes that you might want to pay attention to are the ones that control the display size of the data entry and the attribute that controls the default value and the name.

Say you want to set the number of rows in the text entry area. For this you have the "rows" attribute. Similarly, if you want to set the numbers of columns in the text entry area, you can use the "cols" attribute. The textarea element can also have name and id attribute for the reasons discussed in the last section. Here is a code snippet on how a text area is constructed with all the attributes discussed so far.

```html
<textarea rows="5" cols="80" name="CommentBox" id="CommentBox">
</textarea>
```
As you can see, there are many lines of text within this text area element. Therefore, seting the default text for this area using the value attribute is not possible. Instead, to give a text area element some default value, you have to put that text between the text area tags as shown in the example below:

```html
<textarea rows="5" cols="80" name="CommentBox" id="CommentBox">
Please fill in your comments here.
</textarea>
```

Please note, the information enclosed within a `<textarea>` tag must be plain text and should not
include any HTML markup. 

Here are some points to note about the default text in a `<textarea>` tag:

* The default text preserves all the spaces, returns and other special characters.
* Any markup included within the form control will not be interpreted. 

Here is a complete example of a multi-line text area.

```html
<html>
<head>
<title>Textarea Example</title>
</head>
<body>
<h1 align="center">Textarea Example</h1>
<hr />
<form action="http://www.htmlref.com/scripts/formecho.php"
method="post" name="form1" id="form1">
<strong>Comments:</strong><br />
<textarea name="Comments" id="Comments" rows="8" cols="40">
Your comments go
here.<br />
</textarea><br />
<input type="submit" value="Submit" />
</form>
</body>
</html>
```