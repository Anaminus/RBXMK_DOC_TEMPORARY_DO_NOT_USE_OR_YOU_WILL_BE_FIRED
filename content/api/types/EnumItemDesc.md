+++
weight = 1
title = "EnumItemDesc"
description = "Describes an enum item."
categories = ["API", "Type"]
+++

`type EnumItemDesc = {Index: int?, Name: string, Tags: {string}, Value: int}`

The **EnumitemDesc** type is a table that describes an item of an enum. It
has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Index | [int](/api/types/int) | Hints the order of the item.. |
| Name | [string](/api/types/string) | The name of the item. |
| Tags | { [string](/api/types/string)} | The tags set for the item. |
| Value | [int](/api/types/int) | The numeric value of the item. |