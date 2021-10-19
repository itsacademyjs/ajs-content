Individual cells can span multiple columns too, just like multiple rows as discussed in the previous section. This can be acheived using the `colspan` attribute. The `colspan` attribute accepts a number that indicates how many columns the cell has to span over. The following markdown shows an example:

```html
<table>
  <tr>
    <th colspan="2">Monthly Savings</th>
  </tr>
  <tr>
    <td>January</td>
    <td>$100</td>
  </tr>
  <tr>
    <td>February</td>
    <td>$80</td>
  </tr>
</table>
```
