+++
weight = 1
title = "PropertyDesc"
description = "Describes a property class member."
categories = ["API", "Type"]
+++

`type PropertyDesc = {CanLoad: bool, CanSave: bool, Category: string, MemberType: string, Name: string, ReadSecurity: string, Tags: {string}, ValueType: TypeDesc, WriteSecurity: string}`

The **PropertyDesc** type is a table that describes a property member of a
class. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| CanLoad | [string](/api/types/string) | Whether the property is deserialized. |
| CanSave | [string](/api/types/string) | Whether the property is serialized. |
| MemberType | [string](/api/types/string) | Indicates the type of member. Always "Property". |
| Name | [string](/api/types/string) | The name of the member. |
| ReadSecurity | [string](/api/types/string) | The security context required to get the member. |
| Tags | { [string](/api/types/string)} | The tags set for the member. |
| ValueType | [TypeDesc](/api/types/TypeDesc) | The type of the value of the property. |
| WriteSecurity | [string](/api/types/string) | The security context required to set the member. |