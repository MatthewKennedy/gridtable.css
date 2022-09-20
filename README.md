# GridTable.css

Allows you to build responsive tables using CSS Grid, all while bypassing the quirky table
behaviors everybody hates.

- Use `<a href="some/link">` as table cells for better linking.
- Use Rails / Hotwire `<turbo-frame>` tags within tables without problems.


# Installing

Add the tiny css file to your project or `yarn add gridtable.css` then import the css.


# Usage

Create a table layout using the custom DOM elements provided, Notice that you can use `<a>` tags as table cells
giving a clickable cell without any of the quirky behavior you get with a standard `<table>`.

You can add the layout styling `style="grid-template-columns: 1fr 1fr 1fr 1fr;"` to the `<g-table>` element and it will be inherited by
all table rows, alternatively you can specify different layouts for the head and body by adding the styling to the `<g-thead>` or `<g-tbody>` as needed. If required you can also add the
styling directly to a row to enforce a row specific design.

See the index.html file for more examples.

```html
<g-responsive>
           <!-- Set the cell format using CSS -->
  <g-table style="grid-template-columns: 1fr 1fr 1fr 1fr;">
    <g-thead>
      <g-tr>
        <g-th>Product</g-th>
        <g-th>Price</g-th>
        <g-th>State</g-th>
        <g-th>Actions</g-th>
      </g-tr>
    </g-thead>
    <g-tbody>
      <g-tr>
        <g-td>Adidas FCraft</g-td>
        <g-td>$99.99</g-td>
        <g-td>Available</g-td>
        <g-td>Delete</g-td>
      </g-tr>

      <g-tr>
        <g-td>Adidas Ultra4D</g-td>
        <g-td>$199.99</g-td>
        <g-td>Available</g-td>
        <g-td>Delete</g-td>
      </g-tr>

      <g-tr>
        <g-td>Adidas UltraBoost</g-td>
        <g-td>$201.99</g-td>
        <g-td>Available</g-td>

        <!-- NOTE: You can use a tags as table cells! -->
        <a href="product/3/delete">Delete</a>
      </g-tr>

      <!-- NOTE: these next rows are loaded in later via a turbo frame -->
      <turbo-frame>
        <g-tr>
          <g-td>Nike Air</g-td>
          <g-td>$99.99</g-td>
          <g-td>Available</g-td>
          <g-td>Delete</g-td>
        </g-tr>

        <g-tr>
          <g-td>Nike Zoom</g-td>
          <g-td>$199.99</g-td>
          <g-td>Available</g-td>
          <g-td>Delete</g-td>
        </g-tr>
      </turbo-frame>
    </g-tbody>
  </g-table>
</g-responsive>
```
