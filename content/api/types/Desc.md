+++
weight = 1
title = "Desc"
description = "Describes an API."
categories = ["API", "Type"]
+++

The **Desc** type describes an entire API.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a Desc. |
| [Class](#class) | Method | Gets data about a class. |
| [ClassTag](#classtag) | Method | Gets whether a tag is set for a class. |
| [Classes](#classes) | Method | Gets a list of class names. |
| [Copy](#copy) | Method | Returns a deep copy of the Desc. |
| [Diff](#diff) | Method | Gets the difference between two descriptors. |
| [Enum](#enum) | Method | Gets data about an enum. |
| [EnumItem](#enumitem) | Method | Gets data about an enum item. |
| [EnumItemTag](#enumitemtag) | Method | Gets whether a tag is set for an enum item. |
| [EnumItems](#enumitems) | Method | Gets a list of item names of an enum. |
| [EnumTag](#enumtag) | Method | Gets whether a tag is set for an enum. |
| [EnumTypes](#enumtypes) | Method | Gets enum values generated from the descriptor. |
| [Enums](#enums) | Method | Gets a list of enum names. |
| [Member](#member) | Method | Gets data about a class member. |
| [MemberTag](#membertag) | Method | Gets whether a tag is set for a class member. |
| [Members](#members) | Method | Gets a list of member names of a class. |
| [Patch](#patch) | Method | Transforms the descriptor. |
| [SetClass](#setclass) | Method | Sets data about a class. |
| [SetEnum](#setenum) | Method | Sets data about an enum. |
| [SetEnumItem](#setenumitem) | Method | Sets data about an enum item. |
| [SetMember](#setmember) | Method | Sets data about a class member. |

</div>

# Constructors

----

## new

 `Desc.new(): Desc`

The **new** constructor creates a new Desc.

# Methods

----

## Class

 `Desc:Class(class: string): ClassDesc?`

The **Class** method returns the class of the API corresponding to the
name *class*, or nil if the class does not exist.

## ClassTag

 `Desc:ClassTag(class: string, tag: string): bool?`

Returns whether *tag* is set for the class corresponding to the name
*class*. Returns nil if the class does not exist.

## Classes

 `Desc:Classes(): {string}`

The **Classes** method returns a list of names of all the classes of the
API.

## Copy

 `Desc:Copy(): Desc`

The **Copy** method returns a deep copy of the Desc.

## Diff

 `Desc:Diff(next: Desc?): (diff: DescActions)`

The **Diff** method compares the root descriptor with another and returns
the differences between them. A nil value for *next* is treated the same as
an empty descriptor. The result is a list of actions that describe how to
transform the descriptor into *next*.

## Enum

 `Desc:Enum(enum: string): EnumDesc?`

The **Enum** method returns the enum of the API corresponding to the name
*enum*, or nil if the enum does not exist.

## EnumItem

 `Desc:EnumItem(enum: string, item: string): EnumItemDesc?`

The **EnumItem** method returns the enum item of the API corresponding to
the enum name *enum* and item name *item*, or nil if the enum or item
does not exist.

## EnumItemTag

 `Desc:EnumItemTag(enum: string, item: string, tag: string): bool?`

Returns whether *tag* is set for the enum item corresponding to the name
*item* of the enum named *enum*. Returns nil if the enum or item does
not exist.

## EnumItems

 `Desc:EnumItems(): {string}?`

The **Classes** method returns a list of names of all the items of the
enum corresponding to the name *enum*. Returns nil if the enum does not
exist.

## EnumTag

 `Desc:EnumTag(enum: string, tag: string): bool?`

Returns whether *tag* is set for the enum corresponding to the name
*enum*. Returns nil if the enum does not exist.

## EnumTypes

 `Desc:EnumTypes(): Enums`

The **EnumTypes** method returns a set of enum values generated from the
current state of the Desc. These enums are associated with the Desc, and may be
used by certain properties, so it is important to generate them before operating
on such properties. Additionally, EnumTypes should be called after modifying
enum and enum item descriptors, to regenerate the enum values.

The API of the resulting enums matches that of Roblox's Enums type. A common
pattern is to assign the result of EnumTypes to the "Enum" variable so that it
matches Roblox's API:

```lua
Enum = desc:EnumTypes()
print(Enum.NormalId.Front)

```

## Enums

 `Desc:Enums(): {string}`

The **Enums** method returns a list of names of all the enums of the
API.

## Member

 `Desc:Member(class: string, member: string): MemberDesc?`

The **Member** method returns the class member of the API corresponding to
the class name *enum* and member name *item*, or nil if the class or
member does not exist.

## MemberTag

 `Desc:MemberTag(class: string, member: string, tag: string): bool?`

Returns whether *tag* is set for the class member corresponding to the
name *member* of the class named *class*. Returns nil if the class or
member does not exist.

## Members

 `Desc:Members(): {string}?`

Returns whether *tag* is set for the class member corresponding to the
name *member* of the class named *class*. Returns nil if the class or
member does not exist.

## Patch

 `Desc:Patch(actions: DescActions)`

The **Patch** method transforms the root descriptor according to a list of
actions. Each action in the list is applied in order. Actions that are
incompatible are ignored.

## SetClass

 `Desc:SetClass(class: string, desc: ClassDesc?): bool`

The **SetClass** method sets the fields of the class corresponding to the
name *class*. If the class already exists, then only non-nil fields are
set. Fields with the incorrect type are ignored. If *desc* is nil, then the
class is removed.

Returns false if *desc* is nil and no class exists. Returns true
otherwise.

## SetEnum

 `Desc:SetEnum(enum: string, desc: EnumDesc?): bool`

The **SetEnum** method sets the fields of the enum corresponding to the
name *enum*. If the enum already exists, then only non-nil fields are set.
Fields with the incorrect type are ignored. If *desc* is nil, then the enum
is removed.

Returns false if *desc* is nil and no enum exists. Returns true
otherwise.

## SetEnumItem

 `Desc:SetEnumItem(enum: string, item: string, desc: EnumItemDesc?): bool?`

The **SetEnumItem** method sets the fields of the enum item corresponding
to the name *item* of the enum named *enum*. If the item already
exists, then only non-nil fields are set. Fields with the incorrect type are
ignored. If *desc* is nil, then the enum is removed.

Returns nil if the enum does not exist. Returns false if *desc* is nil
and no item exists. Returns true otherwise.

## SetMember

 `Desc:SetMember(class: string, member: string, desc: ClassDesc?): bool?`

The **SetMember** method sets the fields of the member corresponding to
the name *member* of the class named *class*. If the member already
exists, then only non-nil fields are set. Fields with the incorrect type are
ignored. If *desc* is nil, then the member is removed.

Returns nil if the class does not exist. Returns false if *desc* is nil
and no member exists. Returns true otherwise.