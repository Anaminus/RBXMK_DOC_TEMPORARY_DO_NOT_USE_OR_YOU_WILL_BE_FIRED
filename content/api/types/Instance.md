+++
weight = 1
title = "Instance"
description = "Represents the content of a Roblox instance."
categories = ["API", "Type"]
+++

The **Instance** type represents the content of a Roblox instance. It
provides a similar API to that of Roblox.

See the [Instances section](README.md#user-content-instances) for
details on the implementation of Instances.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a new Instance. |
| [ClassName](#classname) | Property | The class of the instance. |
| [Name](#name) | Property | A name identifying the instance. |
| [Parent](#parent) | Property | The parent instance. |
| [sym.AttrConfig](#symattrconfig) | Symbol | The AttrConfig used by the instance. |
| [sym.Desc](#symdesc) | Symbol | The descriptor used by the instance. |
| [sym.IsService](#symisservice) | Symbol | Whether the instance is a service. |
| [sym.Metadata](#symmetadata) | Symbol | Gets metadata of the DataModel. |
| [sym.Properties](#symproperties) | Symbol | All properties of the instance. |
| [sym.RawAttrConfig](#symrawattrconfig) | Symbol | The direct AttrConfig of the instance. |
| [sym.RawDesc](#symrawdesc) | Symbol | The direct descriptor of the instance. |
| [sym.Reference](#symreference) | Symbol | A reference to the instance. |
| [ClearAllChildren](#clearallchildren) | Method | Remove each child of the instance. |
| [Clone](#clone) | Method | Creates a copy of the instance. |
| [Descend](#descend) | Method | Gets a descendant by name. |
| [Destroy](#destroy) | Method | Removes an instance. |
| [FindFirstAncestor](#findfirstancestor) | Method | Gets an ancestor by name. |
| [FindFirstAncestorOfClass](#findfirstancestorofclass) | Method | Gets an ancestor by class name. |
| [FindFirstAncestorWhichIsA](#findfirstancestorwhichisa) | Method | Gets an ancestor by inherited class name. |
| [FindFirstChild](#findfirstchild) | Method | Gets a child by name. |
| [FindFirstChildOfClass](#findfirstchildofclass) | Method | Gets a child by class name. |
| [FindFirstChildWhichIsA](#findfirstchildwhichisa) | Method | Gets a child by inherited class name. |
| [GetAttribute](#getattribute) | Method | Gets an attribute. |
| [GetAttributes](#getattributes) | Method | Gets all attributes. |
| [GetChildren](#getchildren) | Method | Gets the children. |
| [GetDescendants](#getdescendants) | Method | Gets all descendants. |
| [GetFullName](#getfullname) | Method | Gets a name according to the ancestors of the instance. |
| [GetService](#getservice) | Method | Gets a service instance from the tree. |
| [IsA](#isa) | Method | Gets whether the class inherits from a given class name. |
| [IsAncestorOf](#isancestorof) | Method | Gets whether the instance is an ancestor. |
| [IsDescendantOf](#isdescendantof) | Method | Gets whether the instance is an descendant. |
| [SetAttribute](#setattribute) | Method | Sets an attribute. |
| [SetAttributes](#setattributes) | Method | Sets all attributes. |
| [\_\_index](#__index) | Operator | Gets a property. |
| [\_\_newindex](#__newindex) | Operator | Sets a property. |

</div>

# Constructors

----

## new

 `Instance.new(className: string, parent: Instance?, descriptor: (Desc | bool)?): Instance`

The **new** constructor returns a new Instance of the given class.
*className* sets the [ClassName](/api/types/Instance#classname)
property of the instance. If *parent* is specified, it sets the [Parent](/api/types/Instance#parent) property.

If *desc* is specified, then it sets the [sym.Desc](/api/types/Instance#symdesc)
member. Additionally, new will throw an error if the class does not exist. If no
descriptor is specified, then any class name will be accepted.

If *className* is "DataModel", then *parent* must be nil.

# Properties

----

## ClassName

 `Instance.ClassName: string`

The **ClassName** property gets or sets the class of the instance.

ClassName can be modified, except when the class is "DataModel". Changing the
class of an instance has no additional effects; properties are not transformed
to conform to any descriptors of the class.

## Name

 `Instance.Name: string`

The **Name** property gets or sets a name identifying the instance.

## Parent

 `Instance.Parent: Instance?`

The **Parent** property gets or sets the parent of the instance, which may
be nil.

# Symbols

----

## sym.AttrConfig

 `Instance[sym.AttrConfig]: AttrConfig | bool | nil`

The **AttrConfig** symbol is the [AttrConfig](/api/types/AttrConfig)
being used by the instance. AttrConfig is inherited, the behavior of which is
described in the [Value inheritance](README.md#user-content-value-inheritance)
section.

## sym.Desc

 `Instance[sym.Desc]: Desc | bool | nil`

The **Desc** symbol is the descriptor being used by the instance. Desc is
inherited, the behavior of which is described in the [Value inheritance](README.md#user-content-value-inheritance)
section.

## sym.IsService

 `Instance[sym.IsService]: bool`

The **IsService** symbol indicates whether the instance is a service, such
as Workspace or Lighting. This is used by some formats to determine how to
encode and decode the instance.

## sym.Metadata

 `Instance[sym.Metadata]: Dictionary`

*This member only exists if the instance is of class DataModel.*

The **Metadata** symbol gets or sets the metadata associated with the
DataModel. This metadata is used by certain formats (e.g.
ExplicitAutoJoints).

## sym.Properties

 `Instance[sym.Properties]: Dictionary`

The **Properties** symbol gets or sets all properties of the instance.
Each entry in the table is a property name mapped to the value of the
property.

When getting, properties that would produce an error are ignored.

When setting, properties in the instance that are not in the table are
removed. If any property could not be set, then an error is thrown, and no
properties are set or removed.

## sym.RawAttrConfig

 `Instance[sym.RawAttrConfig]: AttrConfig | bool | nil`

The **RawAttrConfig** symbol is the raw member corresponding to to [sym.AttrConfig](/api/types/Instance#symattrconfig). It is similar to
AttrConfig, except that it considers only the direct value of the current
instance. The exact behavior of RawAttrConfig is described in the [Value inheritance](README.md#user-content-value-inheritance)
section.

## sym.RawDesc

 `Instance[sym.RawDesc]: Desc | bool | nil`

The **RawDesc** symbol is the raw member corresponding to to [sym.Desc](/api/types/Instance#symdesc). It is similar to Desc, except that
it considers only the direct value of the current instance. The exact behavior
of RawDesc is described in the [Value inheritance](README.md#user-content-value-inheritance)
section.

## sym.Reference

 `Instance[sym.Reference]: string`

The **Reference** symbol is a string used to refer to the instance from
within an instance tree. Certain formats use this to encode a reference to an
instance. For example, the RBXMX format will generate random UUIDs for its
references (e.g. "RBX8B658F72923F487FAE2F7437482EF16D").

A reference should not be expected to persist when being encoded or
decoded.

# Methods

----

## ClearAllChildren

 `Instance:ClearAllChildren()`

The **ClearAllChildren** method sets the [Parent](/api/types/Instance#parent) of each child of the instance to nil.

Unlike in Roblox, ClearAllChildren does not affect descendants.

## Clone

 `Instance:Clone(): Instance`

The **Clone** method returns a copy of the instance.

Unlike in Roblox, Clone does not ignore an instance if its Archivable
property is set to false.

## Descend

 `Instance:Descend(...: string): Instance?`

The **Descend** method returns a descendant of the instance by recursively
searching for each name in succession according to [FindFirstChild](/api/types/Instance#findfirstchild). Returns nil if a child
could not be found. Throws an error if no arguments are given.

Descend provides a safe alternative to indexing the children of an instance,
which is not implemented by rbxmk.

```lua
local face = game:Descend("Workspace", "Noob", "Head", "face")
```

## Destroy

 `Instance:Destroy()`

The **Destroy** method sets the [Parent](/api/types/Instance#parent)
of the instance to nil.

Unlike in Roblox, the Parent of the instance remains unlocked. Destroy also
does not affect descendants.

## FindFirstAncestor

 `Instance:FindFirstAncestor(name: string): Instance?`

The **FindFirstAncestor** method returns the first ancestor whose [Name](/api/types/Instance#name) equals *name*, or nil if no such
instance was found.

## FindFirstAncestorOfClass

 `Instance:FindFirstAncestorOfClass(className: string): Instance?`

The **FindFirstAncestorOfClass** method returns the first ancestor of the
instance whose [ClassName](/api/types/Instance#classname) equals
*className*, or nil if no such instance was found.

## FindFirstAncestorWhichIsA

 `Instance:FindFirstAncestorWhichIsA(className: string): Instance?`

The **FindFirstAncestorWhichIsA** method returns the first ancestor of the
instance whose [ClassName](/api/types/Instance#classname) inherits
*className* according to the instance's descriptor, or nil if no such
instance was found. If the instance has no descriptor, then the ClassName is
compared directly.

## FindFirstChild

 `Instance:FindFirstChild(name: string, recurse: bool?): Instance?`

The **FindFirstChild** method returns the first child of the instance
whose [Name](/api/types/Instance#name) equals *name*, or nil if no
such instance was found. If *recurse* is true, then descendants are also
searched, top-down.

## FindFirstChildOfClass

 `Instance:FindFirstChildOfClass(className: string, recurse: bool?): Instance?`

The **FindFirstChildOfClass** method returns the first child of the
instance whose [ClassName](/api/types/Instance#classname) equals
*className*, or nil if no such instance was found. If *recurse* is
true, then descendants are also searched, top-down.

## FindFirstChildWhichIsA

 `Instance:FindFirstChildWhichIsA(className: string, recurse: bool?): Instance?`

The **FindFirstChildWhichIsA** method returns the first child of the
instance whose [ClassName](/api/types/Instance#classname) inherits
*className*, or nil if no such instance was found. If the instance has no
descriptor, then the ClassName is compared directly. If *recurse* is true,
then descendants are also searched, top-down.

## GetAttribute

 `Instance:GetAttribute(attribute: string): any?`

The **GetAttribute** method returns the value of *attribute*, or nil
if the attribute is not found.

This function uses the instance's [sym.AttrConfig](/api/types/Instance#symattrconfig) to select the property
to decode from, which is expected to be string-like. An error is thrown if the
data could not be decoded.

See the [rbxattr format](/api/formats/rbxattr.md) for a list of possible
attribute value types.

The [Attributes](README.md#user-content-attributes) section
provides a more general description of attributes.

## GetAttributes

 `Instance:GetAttributes(): Dictionary`

The **GetAttributes** method returns a dictionary of attribute names
mapped to values.

This function uses the instance's [sym.AttrConfig](/api/types/Instance#symattrconfig) to select the property
to decode from, which is expected to be string-like. An error is thrown if the
data could not be decoded.

See the [rbxattr format](/api/formats/rbxattr.md) for a list of possible
attribute value types.

The [Attributes](README.md#user-content-attributes) section
provides a more general description of attributes.

## GetChildren

 `Instance:GetChildren(): Objects`

The **GetChildren** method returns a list of children of the instance.

## GetDescendants

 `Instance:GetDescendants(): Objects`

The **GetDescendants** method returns a list of descendants of the
instance.

## GetFullName

 `Instance:GetFullName(): string`

The **GetFullName** method returns the concatenation of the [Name](/api/types/Instance#name) of each ancestor of the instance and the
instance itself, separated by `.` characters. If an ancestor is a
DataModel, it is not included.

## GetService

 `Instance:GetService(name: string): Instance`

*This member only exists if the instance is of class DataModel.*

The **GetService** method returns the first child of the DataModel whose
[ClassName](/api/types/Instance#classname) equals *className*. If no
such child exists, then a new instance of *className* is created. The [Name](/api/types/Instance#name) of the instance is set to *className*,
[sym.IsService](/api/types/Instance#symisservice) is set to true, and [Parent](/api/types/Instance#parent) is set to the DataModel.

If the DataModel has a descriptor, then GetService will throw an error if the
created class's descriptor does not have the "Service" tag set.

## IsA

 `Instance:IsA(className: string): bool`

The **IsA** method returns whether the [ClassName](/api/types/Instance#classname) inherits from *className*,
according to the instance's descriptor. If the instance has no descriptor, then
IsA returns whether ClassName equals *className*.

## IsAncestorOf

 `Instance:IsAncestorOf(descendant: Instance?): bool`

The **IsAncestorOf** method returns whether the instance of an ancestor of
*descendant*.

## IsDescendantOf

 `Instance:IsDescendantOf(ancestor: Instance?): bool`

The **IsDescendantOf** method returns whether the instance of a descendant
of *ancestor*.

## SetAttribute

 `Instance:SetAttribute(attribute: string, value: Variant?)`

The **SetAttribute** method sets *attribute* to *value*. If
*value* is nil, then the attribute is removed.

This function uses the instance's [sym.AttrConfig](/api/types/Instance#symattrconfig) to select the property
to decode from, which is expected to be string-like. This function decodes the
serialized attributes, sets the given value, then re-encodes the attributes. An
error is thrown if the data could not be decoded or encoded.

See the [rbxattr format](/api/formats/rbxattr.md) for a list of possible
attribute value types.

The [Attributes](README.md#user-content-attributes) section
provides a more general description of attributes.

## SetAttributes

 `Instance:SetAttributes(attributes: Dictionary)`

The **SetAttributes** method replaces all attributes with the content of
*attributes*, which contains attribute names mapped to values.

This function uses the instance's [sym.AttrConfig](/api/types/Instance#symattrconfig) to select the property
to encode to. An error is thrown if the data could not be encoded.

See the [rbxattr format](/api/formats/rbxattr.md) for a list of possible
attribute value types.

The [Attributes](README.md#user-content-attributes) section
provides a more general description of attributes.

# Operators

----

## \_\_index

 `Instance[property: string]: any?`

The **index** operator gets the value of a property of the instance. If
the instance has a descriptor, then the the properties are enforced by the
descriptor. Otherwise, any property can be any type of value.

## \_\_newindex

 `Instance[property: string] -> (value: any?)`

The **newindex** operator sets the value of a property of the instance. If
the instance has a descriptor, then the the properties are enforced by the
descriptor. Otherwise, any property can be set to any value.