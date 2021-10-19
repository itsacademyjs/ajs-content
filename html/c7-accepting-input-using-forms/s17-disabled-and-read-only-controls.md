The HTML specification has two other attributes to certain form controls: `disabled` and `readonly`. When the disabled attribute is present in a form control element, it turns off the field. Disabled elements will not be submitted, nor may they receive any focus from the keyboard or mouse. The browser might also gray out the disabled form. 

The point of the disabled attribute might not be obvious, but one possible use case is being able to disable the form submission button until the appropriate fields have been filled in. Of course, the capability to dynamically
turn the disabled attribute for a form control on or off requires scripting support.

When the `readonly` attribute is present in a form control element, it prevents the control's value from being changed. A form control set to readonly can be selected by the user but cannot be changed. Selection might even include the form control in the tabbing order. Unlike disabled controls, the values of readonly controls are submitted with the form. You can think of a read-only form control as a visible form of hidden inputs like this:

```<input type="hidden">```. 

According to the HTML specification, the `readonly` attribute is defined for the `<input type="text">`, `<input type="password">`, and `<textarea>` tags, but in practice many browsers support the other fields such as pull-downs, radios, and check boxes.

Like a disabled form control, read-only controls can be changed only through the use of a script.