+++
weight = 110
title = "json"
description = "Operations for handling JSON data."
categories = ["API", "Library"]
+++

The **json** library provides functions for handling JSON data.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [diff](#diff) | Function | Get difference between two JSON values. |
| [fromString](#fromstring) | Function | Converts a string to a JSON value. |
| [patch](#patch) | Function | Tranforms a JSON value according to a patch. |
| [string](#string) | Function | no content for topic "Libraries/json:Fields/string/Summary" |

</div>

# Functions

----

## diff

 `json.diff(prev: JsonValue, next: JsonValue): {JsonPatch}?`

The **diff** function returns a patch that represents the transformation
of *prev* to *next*. This patch can be applied with
`json.patch`.

## fromString

 `json.fromString(string: string): JsonValue`

The **fromString** function attempts to convert *string* to a JSON
value. It is equivalent to `rbxmk.decodeFormat("json", string)`

## patch

 `json.patch(value: JsonValue, patch: JsonPatch): JsonValue`

The **patch** function returns a copy of *value* that has been
transformed according to *patch*.

## string

 `json.string(value: JsonValue): string`

no content for topic "Libraries/json:Fields/string/Description"