+++
weight = 110
title = "string"
description = "Extensions to the standard string library."
categories = ["API", "Library"]
+++

The **string** library is an extension to the standard library that
includes the same additions to
[Roblox's string library](https://developer.roblox.com/en-us/api-reference/lua-docs/string).

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [split](#split) | Function | Splits a string into a list of substrings. |

</div>

# Functions

----

## split

 `string.split(s: string, sep: string? = ","): {string}`

The **split** function splits *s* into substrings separated by
*sep*.

If *sep* is nil, or if *sep* is not nil but not in *s*, then
split returns a table with *s* as its only element.

If *sep* is empty, then *s* is split after each UTF-8 sequence.

**Note**: Roblox's implementation splits per byte, while this
implementation splits per UTF-8 character.