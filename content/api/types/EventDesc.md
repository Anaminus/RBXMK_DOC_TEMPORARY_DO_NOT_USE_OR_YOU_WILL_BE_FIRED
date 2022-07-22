+++
weight = 1
title = "EventDesc"
description = "Describes an event class member."
categories = ["API", "Type"]
+++

`type EventDesc = {MemberType: string, Name: string, Parameters: {ParameterDesc}, Security: string, Tags: {string}}`

The **EventDesc** type is a table that describes a event member of a
class. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| MemberType | [string](/api/types/string) | Indicates the type of member. Always "Event". |
| Name | [string](/api/types/string) | The name of the member. |
| Parameters | { [ParameterDesc](/api/types/ParameterDesc)} | The parameters of the event. |
| Security | [string](/api/types/string) | The security context required to get the member. |
| Tags | { [string](/api/types/string)} | The tags set for the member. |