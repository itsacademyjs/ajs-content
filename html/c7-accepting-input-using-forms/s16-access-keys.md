Form accessibility can be further improved by using the `accesskey` attribute. The `accesskey` attribute for form fields is an important accessibility improvement, just like the tabbing order we learnt about in the previous section. Setting the value of the key to a character creates an accelerator key that can activate the form control associated with the element. Generally, the key must be pressed in combination with the ALT or OPTION key to activate the field. 

An example of how this attribute might be used is shown in the following markdown:

```html
<label>Customer <u>N</u>ame:
<input type="text" accesskey="N" size="25" />
</label>
```

Notice how a `<u>` tag, used to underline text, is used to highlight the letter that will activate the field. This is the common practice to indicate accelerator keys in a Windows GUI. A more CSS-aware approach to indicating accesskey bindings is shown here:

```html
<label>Customer <span class="accesskeyindication">N</span>ame:
<input type="text" accesskey="N" size="25" />
</label>
```

From this, you would set the class to indicate the accesskeyindication in whatever manner you wanted. Regardless, both these methods of indicating access keys are redundant since modern browsers have their own way of highlighting access keys.