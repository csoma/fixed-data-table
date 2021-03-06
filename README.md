Fixed Data Tables for React
====================================

FixedDataTable is a React component for building and presenting data in a flexible, powerful way. It supports standard table features, like headers, columns, rows, header groupings, and both fixed-position and scrolling columns.

The table was designed to handle thousands rows of data without sacrificing performance. Scrolling smoothly is a first-class goal of FixedDataTable and it's architected in a way to allow for flexibility and extensibilty.

Features of FixedDataTable:
* Fixed headers and footer
* Both fixed and scrollable columns
* Handling huge amounts of data
* Variable row heights (with adaptive scroll positions)
* Column resizing
* Performant scrolling
* Customizable styling
* Jumping to a row or column

Things that are FixedDataTable doesn't do:
* FixedDataTable does not provide a layout reflow mechanism or calculates content layout information such as width and height of the cell contents. The developer has to provide the layout information to the table instead.
* FixedDataTable does not handle sorting of data. Instead it allows the developer to supply data getters that can be sort-, filter-, or tail-loading-aware.
* FixedDataTable does not fetch the data (see above)
* FixedDataTable does not support touch devices, but eventually will.

Getting started
---------------

Install `fixed-data-table` using npm.

```shell
npm install fixed-data-table
```

Then require it into any module.

```javascript
var React = require('react');
var FixedDataTable = require('fixed-data-table');

var Table = FixedDataTable.Table;
var Column = FixedDataTable.Column;

// Table data as a list of array.
var rows = [
  ['a1', 'b1', 'c1'],
  ['a2', 'b3', 'c2'],
  ['a3', 'b3', 'c3'],
  ..... /// and more
];

function rowGetter(rowIndex) {
  return rows[rowIndex];
}

React.render(
  <Table
    rowHeight={50}
    rowGetter={rowGetter}
    rowsCount={rows.length}
    width={5000}
    height={5000}
    headerHeight={50}>
    <Column
      label="Col 1"
      width={3000}
      dataKey={0}
    />
    <Column
      label="Col 2"
      width={2000}
      dataKey={1}
    />
  </Table>,
  document.getElementById('example')
);
```


Contributions
------------

Use [Github issues](https://github.com/facebook/fixed-data-table-experimental/issues) for requests.

We actively welcome pull requests; learn how to [contribute](./CONTRIBUTING.md).


Changelog
---------

Changes are tracked as [Github releases](https://github.com/facebook/fixed-data-table-experimental/releases).


License
-------

`FixedDataTable` is [BSD-licensed](./LICENSE). We also provide an additional [patent grant](./PATENTS).
