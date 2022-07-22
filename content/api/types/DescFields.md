+++
weight = 1
title = "DescFields"
description = "A collection of DescAction fields."
categories = ["API", "Type"]
+++

`type DescFields = {[string]: any}`

The **DescFields** type is a collection of DescAction fields. Each element
is a pair that maps a field name to a value.

The following value types are allowed:

| Type | Notes |
| --- | --- |
| bool |  |
| number |  |
| string |  |
| TypeDesc | Table must contain "Category" and "Name" fields. |
| ParameterDesc | Field name must be "Parameters". |
| {string} | Field name must be "Tags". |