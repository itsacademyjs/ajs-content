A doctype is basically an instruction that informs the browser about the kind of markup language your web page is written in. 

According the HTML specifications, it is very important that your HTML documents have the doctype declaration to ensure that your web page is displayed the way you intended it to be displayed.

It is case-insensitive and should be written on the top of the document as shown below:

```html
<!DOCTYPE html>
<html>
  
<body>
    <h1>AcademyJS</h1>
</body>
  
</html>
```

In the older version of HTML, HTML 4.01, which also happens to be the most popular version in the 2000s, the usage of DOCTYPE declaration was based on creating a reference to a DTD or document type definition. 

The DTD is responsible for specifying the rules for the Standard Generalized Markup Language so that the browser processes the content correctly. HTML 4.01 was based off of SGML. 

In HTML 5, however, there isn’t any need for a reference to DTD. This is because HTML 5 is not based on SGML. Instead, the declaration is only required to tell the browser what the standard mode for writing documents is.