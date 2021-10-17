As described in the previous sections, the input tag is very complex and has several type. Let us start with the simplest type - text.

You can accept a single line of text using an input box as shown in the code below:

```html
<input type="text" name="UserName" id="UserName">
```

Before we move any further, let us briefly discuss about the issues surrounding two attributes that you see in the example above - the name attribute and the id attribute.

These two attributes can be used in your `<form>` tag itself. They can also be used in the individual elements of the form, also called as "fields". An example of using these two attributes in a form field is shown above. 

Originally only the name attribute was supported. This was used for two purposes.

* The name attribute would be used to create the name-value pairs submitted to the server.
* The name would be used in the program or script that handled the form input.

The id attribute was introduced much later, but it's not very new either. The id attribute first came about with the release of HTML 4 and XHTML.

The main use of the id attribute is for the following references:
* Reference an element in your CSS files.
* Reference an element or form field in your JavaScript.

The name, however is used for server-side programs as well the JavaScript for client side interaction.

You may notice there is some overlap here - both id and name are used in the JavaScript for client side interaction and logic. This is why, wherever possible, it is best practice to set the name and id to the same value. In most cases, they are exactly the same. But, there are inconsistencies in other types of inputs, such as check boxes and radio buttons. This difference is explained very well in the sections that cover these inputs. You can skip ahead and read about them by clicking [here]() and [here]().

While creating input forms in XHTML, you may notice a validation error. This is because the name attribute is deprecated in XHTML, but you may also not see a validation error at all, because most modern browsers ignore it, since scripting may not be possible with the name tag.