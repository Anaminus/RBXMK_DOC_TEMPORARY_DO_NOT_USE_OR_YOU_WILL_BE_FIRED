+++
weight = 1
title = "CallbackDesc"
description = "Describes a callback."
categories = ["API", "Type"]
+++

`type CallbackDesc = {MemberType: string, Name: string, Parameters: {ParameterDesc}, ReturnType: TypeDesc, Security: string, Tags: {string}}`

The **CallbackDesc** type is a table that describes a callback member of a
class. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| MemberType | [string](/api/types/string) | Indicates the type of member. Always "Callback". |
| Name | [string](/api/types/string) | The name of the member. |
| Parameters | { [ParameterDesc](/api/types/ParameterDesc)} | The parameters of the callback. |
| ReturnType | [TypeDesc](/api/types/TypeDesc) | The type of the value returned by the callback. |
| Security | [string](/api/types/string) | The security context required to set the member. |
| Tags | { [string](/api/types/string)} | The tags set for the member. |