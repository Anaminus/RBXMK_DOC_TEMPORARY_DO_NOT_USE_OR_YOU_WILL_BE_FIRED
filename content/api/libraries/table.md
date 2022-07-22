+++
weight = 110
title = "table"
description = "Extensions to the standard table library."
categories = ["API", "Library"]
+++

The **table** library is an extension to the standard library that
includes the same additions to
[Roblox's table library](https://developer.roblox.com/en-us/api-reference/lua-docs/table).

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [clear](#clear) | Function | Removes all entries from a table. |
| [create](#create) | Function | Creates a new table with a preallocated capacity. |
| [find](#find) | Function | Find the index of a value in a table. |
| [move](#move) | Function | Copies the entries in a table. |
| [pack](#pack) | Function | Packs arguments into a table. |
| [unpack](#unpack) | Function | Unpacks a table into arguments. |

</div>

# Functions

----

## clear

 `table.clear(t: table)`

The **clear** function removes all the entries from *t*.

## create

 `table.create(cap: integer, value: any?): table`

The **create** function returns a table with the array part allocated with
a capacity of *cap*. Each entry in the array is optionally filled with
*value*.

## find

 `table.find(t: table, value: any, init: integer? = 1): integer?`

The **find** function returns the index in *t* of the first
occurrence of *value*, or nil if *value* was not found. Starts at
index *init*, or 1 if unspecified.

## move

 `table.move(a1: table, f: integer, e: integer, t: integer, a2: table?): table`

The **move** function copies elements from *a1* to *a2*,
performing the equivalent to the multiple assignment

```
a2[t], ... = a1[f], ..., a1[e]
```

The default for *a2* is *a1*. The destination range can overlap the
source range. Returns *a2*.

## pack

 `table.pack(...: any?): table`

The **pack** function returns a table with each argument stored at keys 1,
2, etc. Also sets field "n" to the number of arguments. Note that the resulting
table may not be a sequence.

## unpack

 `table.unpack(list: table, i: integer?, j: integer?): (...: any?)`

Returns the elements from *list*, equivalent to

```
list[i], list[i+1], ..., list[j]
```

By default, *i* is 1 and *j* is the length of *list*.