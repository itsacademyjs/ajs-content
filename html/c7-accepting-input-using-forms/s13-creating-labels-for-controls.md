To improve the accessibility of your page, you might want to use labels along with your check boxes and radio button groups. This provides some direct accessibility benefits such as the ones listed below:

* Screen reader users and other user agents will read aloud the label when the radio button or check box is hovered.
* Users who have difficulty clicking on very small regions will benefit from usage of labels - because when a user clicks on the text within the <label> element, it also toggles the input that the label is associated with. In other words, using labels will increase the hit area of the button. This benefit, however, is not very substantial since the same results can be achieved by styling the radio button or the check box using CSS. 

The following example illustrates the usage of multiple label elements and how the label elements associate with teh radio buttons or check boxes. Please notice that the `for` attribute of the label should be equal to the `id` of the radio button that it is associated with.

```html
<form action="/action_page.php">
  <input type="radio" id="html" name="fav_language" value="HTML">
  <label for="html">HTML</label><br>
  <input type="radio" id="css" name="fav_language" value="CSS">
  <label for="css">CSS</label><br>
  <input type="radio" id="javascript" name="fav_language" value="JavaScript">
  <label for="javascript">JavaScript</label><br><br>
  <input type="submit" value="Submit">
</form>
```