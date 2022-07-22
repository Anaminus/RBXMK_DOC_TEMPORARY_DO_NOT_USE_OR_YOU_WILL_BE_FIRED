+++
weight = 1
title = "ClassDesc"
description = "Describes a class."
categories = ["API", "Type"]
+++

`type ClassDesc = {MemoryCategory: string, Name: string, Superclass: string, Tags: {string}}`

The **ClassDesc** type is a table that describes a class. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| MemoryCategory | [string](/api/types/string) | The category of the class. |
| Name | [string](/api/types/string) | The name of the class. |
| Superclass | [string](/api/types/string) | The name of the class from which the current class inherits. |
| Tags | { [string](/api/types/string)} | The tags set for the class. |