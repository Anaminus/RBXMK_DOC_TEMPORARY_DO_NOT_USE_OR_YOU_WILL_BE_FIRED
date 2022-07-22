+++
weight = 1
title = "Enum"
description = "A set of named values."
categories = ["API", "Type"]
+++

The **Enum** type is a set of named values.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [GetEnumItems](#getenumitems) | Method | Returns the items of the enum. |
| [\_\_index](#__index) | Operator | Gets an item by name. |

</div>

# Methods

----

## GetEnumItems

 `Enum:GetEnumItems(): {EnumItem}`

The **GetEnumItems** method returns a list of items of the enum.

# Operators

----

## \_\_index

 `Enum[name: string]: EnumItem`

The **index** operator returns an item of the enum indexed by name.