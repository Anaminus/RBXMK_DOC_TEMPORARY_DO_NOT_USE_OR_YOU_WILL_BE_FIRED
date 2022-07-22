+++
weight = 1
title = "FunctionDesc"
description = "Describes a function class member."
categories = ["API", "Type"]
+++

`type FunctionDesc = {MemberType: string, Name: string, Parameters: {ParameterDesc}, ReturnType: TypeDesc, Security: string, Tags: {string}}`

The **FunctionDesc** type is a table that describes a function member of a
class. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| MemberType | [string](/api/types/string) | Indicates the type of member. Always "Function". |
| Name | [string](/api/types/string) | The name of the member. |
| ReturnType | [TypeDesc](/api/types/TypeDesc) | The type of the value returned by the function. |
| Security | [string](/api/types/string) | The security context required to set the member. |
| Parameters | { [ParameterDesc](/api/types/ParameterDesc)} | The parameters of the function. |
| Tags | { [string](/api/types/string)} | The tags set for the member. |