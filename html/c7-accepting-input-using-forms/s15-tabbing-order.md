Most people browse the internet without using a pointing device like a mouse. Hence, it is important to improve accessibility to such folks using proper sequence of items, so tabbing through your website becomes easier. Maintaining tabbing order is even more important with forms because almost everyone tabs through fields as they enter their inputs.

To really understand why tabbing order is so important, let's look at a bad example and then a good example of tabbing orders in forms. The code below has four form field elements. You can immediately notice that the form has no tabbing order, and the fields are out of sequence. None of the fields have a tab index, which can be given using the `tabindex` property.

```html
<div class="formfield">
<input name="FName"/>
<font>First Name</font>
</div>
<div>
<input name="Email"/>
<font>Email</font>
</div>
<div>
<input name="LName"/>
<font>Last Name</font>
</div>
<div>
<input name="Email2"/>
<font>Confirm Email</font>
</div>
```

In the following example, every element in the form is given the tab index attribute. You might wonder why the tab index starts from 100 rather than 1. You have to keep in mind that the form you have in your HTML document might not be the only content on the page. A higher number is used so that the logical ordering is preserved once the first member of the form is focused.

```html
<div class="formfield">
<input name="FName" tabindex="100" />
<font>First Name</font>
</div>
<div>
<input name="Email" tabindex="300" />
<font>Email</font>
</div>
<div>
<input name="LName" tabindex="200" />
<font>Last Name</font>
</div>
<div>
<input name="Email2"  onblur="validateemail();" tabindex="400" />
<font>Confirm Email</font>
</div>
```
