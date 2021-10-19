The `<table>` HTML element represents tabular data — that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data.

```html
<table>
    <thead>
        <tr>
            <th colspan="2">The table header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
        </tr>
    </tbody>
</table>
```
## Output
---
<table>
    <thead>
        <tr>
            <th colspan="2">The table header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
        </tr>
    </tbody>
</table>

---

Tables might be very useful to display data that involves several parameters or attributes, or data that requires to be compared. Think about all the times when you had to plan something that required more than just a list of item, every time you pulled up a spreadsheet to organize data.

Although tables are very useful in many cases, there are some situations where you might not want to use a table. Here are some things to keep in mind when you are using tables: 

* It is highly discouraged to not use tables for layout purposes! Remember that your HTML document is only supposed to have the structure of your document and not the layout. Layout tables reduce accessibility for visually impaired users because:
    * Screenreaders, used by blind people, interpret the tags that exist in an HTML page and read out the contents to the user. 
    * Because tables are not the right tool for layout, and the markup is more complex than with CSS layout techniques, the screenreaders' output will be confusing to their users.

* Yet another reason to avoid tables for layout purposes is tag soup. table layouts generally involve more complex markup structures than proper layout techniques. This can result in the code being harder to write, read, maintain, upgrade and debug.
* The last reason is probably the most important - tables are not automatically responsive. When you use proper layout containers (such as `<header>`, `<section>`, `<article>`, or `<div>`), their width defaults to 100% of their parent element. But tables on the other hand are sized according to their content by default. This means you would have to style your tables mandatorily, otherwise they would not be responsive.