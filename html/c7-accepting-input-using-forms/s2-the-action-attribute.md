The action attribute tells the browser how to handle the form input. The value of the action attribute is usually equal to some program in your server that will handle the form data. This program can be some script that decodes the value provided in the form by the user.

Let us consider an example to understand this better. Look at the following code sample:
 
```html
<form action="http://www.democompany.com/cgi-bin/post-query.pl" method="post">
```

As you can see, the above code has the action attribute pointing to a script called `post-query.pl`.

The value of the action attribute can also be a relative URL as shown in the example below:

```html
<form action="../cgi-bin/post-query.pl" method="post">
```

There might be a case where there is no way to use a program from a remotely hosted server. In such cases, you can create another version of the form using a `mailto` URL as shown in the code snippet below.

```html
<form action="mailto:formtest@democompany.com" method="post" enctype="text/plain">
```

It is even possible to use an extended form of mailto URL, which is supported
by some browsers. For example, 

```html
<form action="mailto:formtest@democompany.com?
Subject="Comment%20Form%20Result" method="post"
enctype="text/plain">
```

In the above code, %20 is simply the encoding of the space character.

Although the mailto URL style form seems the best way to do things, not all browsers support this properly and many users may not have their e-mail environment set up in such a way to allow this, which is why it is not recommended. 

Even if the browser supports the mailto style, the data should always be passed using the post method. We will learn more about the method attribute in the next section.

It also might be useful to encode the data
differently by setting it to use text/plain encoding rather than the default style, which is a cryptic encoding style similar to how URLs look.