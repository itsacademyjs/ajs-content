In the last section, you have seen that it is also important to specify how the form will be submitted to the specified address or URL, which is provided to the action attribute.

The action attribute tells the browser "where" the form data has to be sent, but the browser also needs to be told "how" the data will be sent. That's where the method attribute comes into picture.

How the data will be submitted is handled by the method attribute. There are two acceptable values for the method attribute: get and post.

These two methods are the HTTP methods that a browser uses to "talk" to a server. You can read more about HTTP methods in details [here]().

Also, an important thing to remember is that if the method attribute remains unspecified, most browsers should default to the get method.
