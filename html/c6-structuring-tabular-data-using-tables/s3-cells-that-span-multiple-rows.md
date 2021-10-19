You might want individual cells to span over multiple rows or columns. This has several use cases, such as rosters, financial reports, titles for tables, and so on. Cells can span over multiple rows as well as multiple columns. You can make your cell span over multiple rows using the `rowspan` attribute. The `rowspan` attribute takes a number that indicates how many rows this particular cell has to span over. The following markdown illustrates how `rowspan` attribute works.

```html
<table>
  <tr>
    <th>Month</th>
    <th>Savings</th>
    <th>Savings for holiday!</th>
  </tr>
  <tr>
    <td>January</td>
    <td>$100</td>
    <td rowspan="2">$50</td>
  </tr>
  <tr>
    <td>February</td>
    <td>$80</td>
  </tr>
</table>
```