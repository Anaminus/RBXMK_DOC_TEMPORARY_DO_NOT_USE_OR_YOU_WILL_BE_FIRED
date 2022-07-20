+++
weight = 100
title = "table"
+++

The **table** library provides functions for manipulating tables.

Most functions assume that the table is an array, where "length" refers to
the result of the `#` operator.

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [concat](#concat) | Function | Concatenates each element as a string. |
| [insert](#insert) | Function | Inserts an element.<br>Appends an element. |
| [maxn](#maxn) | Function | Returns the largest positive numerical index. |
| [remove](#remove) | Function | Removes an element. |
| [sort](#sort) | Function | Sorts elements. |

</div>

# Functions

----

## concat

 `table.concat(t: {string | number}, sep: string? = "", i: integer? = 1, j: integer? = #t): string`

The **concat** function concatenates each element within the table from
*i* to *j*. Each element must be a string or a number. *sep* is
concatenated between each element. An empty string is returned if *i* is
greater than *j*.

## insert

 `table.insert(t: table, index: integer, value: any)`

The **insert** function inserts *value* into *t* at
*index*. Each element after *index* is shifted upward to make
room.

 `table.insert(t: table, value: any)`

The **insert** function appends *value* to the end of *t*, such
that the index is the length *t* plus one.

## maxn

 `table.maxn(t: table): integer`

The **maxn** function returns the largest positive numerical index in
*t*, or 0 if none can be found.

## remove

 `table.remove(t: table, index: integer? = #t): any`

The **remove** function removes the element at *index* from *t*.
Each element after *index* is shifted downward to close the gap. Returns
the removed element.

## sort

 `table.sort(t: table, comp: (a: any, b: any) -> (boolean)?)`

The **sort** function sorts the elements in *t* in-place from index 1
to the length of *t*. If *comp* is specified, then it must return true
when *a* is less than *b*. If *comp* is unspecified, then the
`<` operator is used instead.

The sorting algorithm is not stable. Elements considered equal may have their
relative positions changed.