+++
weight = 1
title = "Enums"
description = "A collection of Enum values."
categories = ["API", "Type"]
+++

The **Enums** type is a collection of Enum values.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [GetEnums](#getenums) | Method | Returns a list of Enum values. |
| [\_\_index](#__index) | Operator | Gets an Enum by name. |

</div>

# Methods

----

## GetEnums

 `Enums:GetEnums(): {Enum}`

The **GetEnums** method returns a list of Enum values in the
collection.

# Operators

----

## \_\_index

 `Enums[name: string]: Enum`

The **index** operator returns an enum in the collection indexed by
name.