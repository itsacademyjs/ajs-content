A newer addition to the input element that now is part of the HTML and XHTML specifications is the capability to set the type attribute to file. This form control is used for file uploading. The field generally consists of a text entry box for a filename that can be manipulated with the size and maxlength attributes, as well as a button immediately to the right of the field, which usually is labeled "Browse." 

Pressing the Browse button enables the user to browse the local system to find a file to specify for upload. The logistics of how a file is selected depends on the user agent.

```html
<html>
<head>
<title>File Upload Test</title>
<meta http-equiv="content-type" content="text/html; charset=ISO-8859-1" />
</head>
<body>
<h1 align="center">File Upload System </h1>
<hr />
<form action="http://www.example.com/scripts/fileupload.php" method="post"
enctype="multipart/form-data" name="form1" id="form1">
<strong>File Description:</strong><br />
<input type="text" name="Description" id="Description" size="50"
maxlength="100" />
<br /><br />
<strong>Specify File to Post:</strong><br />
<input type="file" name="FileName" id="FileName" />
<hr />
<input type="submit" value="Send it" name="SubmitButton"
id="SubmitButton" />
<input type="reset" value="Reset Form" />
</form>
</body>
</html>
```