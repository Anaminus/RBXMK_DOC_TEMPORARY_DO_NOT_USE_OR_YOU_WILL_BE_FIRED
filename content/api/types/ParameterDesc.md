+++
weight = 1
title = "ParameterDesc"
description = "Describes a parameter."
categories = ["API", "Type"]
+++

`type ParameterDesc = {Default: string?, Name: string, Type: TypeDesc}`

The **ParameterDesc** type describes a parameter of a function, event, or
callback member. It has the following members:

| Field | Type | Description |
| --- | --- | --- |
| Type | [TypeDesc](/api/types/TypeDesc) | The type of the parameter. |
| Name | [string](/api/types/string) | The name of the parameter. |
| Default | [string](/api/types/string)? | Describes the default value of the parameter. If nil, then the parameter has no default value. |