There are six levels of text heading in HTML - `<h1>` to `<h6>` HTML elements.

`<h1>` is the highest section level and hence has the larger text and `<h6>` is the lowest and the smallest font size.

## Some points to note about heading elements

* Certain user agents and apps can parse through your HTML document and automatically create a table of contents based on the heading elements. So having proper heading elements in your page is a great way to increase accessibility.
* Never use heading elements to resize text. Instead, use the CSS font-size property. Heading elements should only represent semantic meaning, always!
* Another good practice that most developers do not follow is to avoid jumping or skipping levels of heading. It is recommended that you always start from `<h1>`, followed by `<h2>` and so on, instead of skipping levels.
* Yet another best practice is to use only one `<h1>` per page - meaning each of your HTML documents should have only one `<h1>` tag, preferably something that concisely describes the overall purpose of the content.

Of course, these are only best practices and accepted rules. You can break them if you want. 

For example, using more than one `<h1>` is allowed by the HTML specification, but is not considered a best practice. Using only one `<h1>` is beneficial, especially for users who use screenreaders and other narration based softwares.

Now there might be cases where you would want to use multiple `<h1>` elements in your document. And there is something in the HTML specifications about using multiple `<h1>` elements.

If your document forms an outline of the whole document by using `<section>` elements, then it would be perfectly alright to use multiple `<h1>` elements. 

Why? The answer lies in how most screen-readers and accessibility softwares would read this kind of information. 

Multiple `<h1>` tags separated by different sections would be parsed as subheadings if your document forms the outline specified in the HTML specification. 

Unfortunately, this functionality has never been implemented. So it's better to just stick to the good ol' single `<h1>` tag per document.

Example:

```html
<h1>Heading elements</h1>
<h2>Summary</h2>
<p>Some text here...</p>

<h2>Examples</h2>
<h3>Example 1</h3>
<p>Some text here...</p>

<h3>Example 2</h3>
<p>Some text here...</p>

<h2>See also</h2>
<p>Some text here...</p>
```

This is how the output would look like in your browser.

---
<h1>Heading elements</h1>
<h2>Summary</h2>
<p>Some text here...</p>

<h2>Examples</h2>
<h3>Example 1</h3>
<p>Some text here...</p>

<h3>Example 2</h3>
<p>Some text here...</p>

<h2>See also</h2>
<p>Some text here...</p>

---