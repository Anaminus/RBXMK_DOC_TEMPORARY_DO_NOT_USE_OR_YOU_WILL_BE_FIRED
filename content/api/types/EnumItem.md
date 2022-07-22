+++
weight = 1
title = "EnumItem"
description = "A single item of an Enum."
categories = ["API", "Type"]
+++

The **EnumItem** type represents a single item of an Enum.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [EnumType](#enumtype) | Property | The Enum of the item. |
| [Name](#name) | Property | no content for topic "Types/EnumItem:Properties/Name/Summary" |
| [Value](#value) | Property | no content for topic "Types/EnumItem:Properties/Value/Summary" |
| [IsA](#isa) | Method | Returns whether the item belongs to an enum. |

</div>

# Properties

----

## EnumType

 `EnumItem.EnumType: Enum [readonly]`

The **EnumType** field returns the Enum of the item.

## Name

 `EnumItem.Name: string [readonly]`

The **Name** field returns the name of the item.

## Value

 `EnumItem.Value: int [readonly]`

The **Value** field returns the value of the item.

# Methods

----

## IsA

 `EnumItem:IsA(enumName: string): bool`

The **IsA** method returns whether the item belongs to an enum of the name
*enumName*.