+++
weight = 1
title = "DescAction"
description = "An action that transforms a descriptor."
categories = ["API", "Type"]
+++

The **DescAction** type describes a single action that transforms a
descriptor.

A DescAction can be created with the [DescAction.new](/api/types/DescAction#new) constructor. It is also returned
from the [Desc.Diff](/api/types/Desc#diff) method and the [desc-patch.json](/api/formats/desc-patch.json.md) format.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a new DescAction. |
| [Element](#element) | Property | The type of element. |
| [Primary](#primary) | Property | The name of the primary element. |
| [Secondary](#secondary) | Property | The name of the secondary element. |
| [Type](#type) | Property | The type of transformation. |
| [Field](#field) | Method | Gets a field. |
| [Fields](#fields) | Method | Gets all fields. |
| [SetField](#setfield) | Method | Sets a field. |
| [SetFields](#setfields) | Method | Sets all fields. |

</div>

# Constructors

----

## new

 `DescAction.new(type: Enum.DescActionType, element: Enum.DescActionElement): DescAction`

The **new** constructor returns a new DescAction initialized with a type
and an element.

# Properties

----

## Element

 `DescAction.Element: Enum.DescActionElement`

The **Element** property is the type of element to which the action
applies.

## Primary

 `DescAction.Primary: string`

The **Primary** property is the name of the primary element. For example,
the class name or enum name.

## Secondary

 `DescAction.Secondary: string`

The **Secondary** property is the name of the secondary element. For
example, the name of a class member or enum item. An empty string indicates that
the action applies to the primary element.

## Type

 `DescAction.Type: Enum.DescActionType`

The **Type** property is the type of transformation performed by the
action.

# Methods

----

## Field

 `DescAction:Field(name: string): any`

The **Field** method returns the value of the *name* field, or nil if
the action has no such field.

## Fields

 `DescAction:Fields(): {[string]: DescFields}`

The **Fields** method returns a collection of field names mapped to
values.

## SetField

 `DescAction:SetField(name: string, value: any)`

The **SetField** method sets the value of the *name* field to
*value*.

## SetFields

 `DescAction:SetFields(fields: {[string]: any})`

The **SetFields** method replaces all fields of the action with
*fields*.