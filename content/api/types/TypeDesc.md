+++
weight = 1
title = "TypeDesc"
description = "Describes a type."
categories = ["API", "Type"]
+++

`type TypeDesc = {Category: string, Name: string}`

The **TypeDesc** type is a table that describes a value type. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Category | [string](/api/types/string) | The category of the type. |
| Name | [string](/api/types/string) | The name of the type. |

Certain categories are treated specially:

- **Class**: Name is the name of a class. A value of the type is expected
  to be an Instance of the class.
- **Enum**: Name is the name of an enum. A value of the type is expected to
  be an enum item of the enum.