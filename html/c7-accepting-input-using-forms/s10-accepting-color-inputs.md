You might need a form field that let's users pick a color. Now you could do this in several ways - use a radio button group, perhaps a select menu, or even a single line input text entry box where the user can enter the hex code of the color he wants to choose. A much betwen way of taking color input is by using the color input type.

`<input>` elements of type color provide an interface element that lets a user specify a color. The interface gives the user an option to choose the color either by using a visual color picker interface or by entering the color into a text field in `#rrggbb` hexadecimal format.

Only simple colors (without alpha channel) are allowed using this interface. CSS colors, however, has a lot more formats, e.g. color names, functional notations and a hexadecimal format with an alpha channel to control the opacity or transparency of the color.

The look and feel of the color input interface may vary substantially, as expected, from one browser to another.

The following markdown illustrates an example of a color input.

```html
<div>
    <input type="color" id="head" name="head"
           value="#e66465">
    <label for="head">Head</label>
</div>

<div>
    <input type="color" id="body" name="body"
            value="#f6b73c">
    <label for="body">Body</label>
</div>

```

Notice that you can pre-select the color by using the value attribute. The value attribute has to be provided with the hex value of the color in `#rrggbb` format.