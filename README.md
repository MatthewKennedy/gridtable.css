# GridTable.css

GridTable.css allows you to easily build responsive tables based on CSS Grid, all while bypassing the quirky table
behaviors everybody hates.


## Overview

- Allows you to set `<a href="some/link">Some Content</a>` as a table cell for better links.
- Wrap table rows with Rails / Hotwire tags without problems.
- Uses custom HTML DOM elements to cut down on css class stuffing.


# Installing

Add the tiny css file to your project or `yarn add gridtable.css` then import the css into your project.


# Usage

Create a table layout using the custom DOM elements provided, Notice that you can use `<a>` tags as table cells
giving a clickable cell without any of the quirky behavior you get with a standard `<table>`.

You can add the layout styling `style="grid-template-columns: 1fr 1fr 1fr 1fr;"` to the `<g-table>` element and it will be inherited by
all table rows, alternatively you can specify different layouts for the head and body by adding the styling to the `<g-thead>` or `<g-tbody>` as needed. If required you can also add the
styling directly to a row to enforce a row specific design.

See example below and more in the index.html file.

```html
<g-responsive> <!-- Wrap the table in the responsive tag -->

           <!--
           IMPORTANT: Set the cell format using CSS Grid Template Columns.
                      You can set this on the <g-table> tag, and it will be
                      inherited through the <g-head> and <g-body> rows. Alternatively
                      you can set this independently on the <g-thead> and <g-tbody> -->
  <g-table style="grid-template-columns: 1fr 1fr 1fr 1fr;">
    <g-thead>
      <g-tr>
        <g-th>Product</g-th>
        <g-th>Price</g-th>

              <!--
              NOTE: You can override the grid-column-template
                    telling a cell to span 2 columns -->
        <g-th style="grid-column: span 2;">State</g-th>
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

        <!--
        NOTE: You can use <a> tags as table cells -->
        <a href="product/3/delete">Delete</a>
      </g-tr>

      <!--
      NOTE: These next rows are loaded in later via a turbo frame,
            and the table cell formatting is carried through fine. -->
      <turbo-frame id="some_id_1">
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
