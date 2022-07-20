+++
weight = 110
title = "sym"
+++

The **sym** library contains **Symbol** values. A symbol is a unique
identifier that can be used to access certain metadata fields of an [Instance](type:Instance).

An instance can be indexed with a symbol to get a metadata value in the same
way it can be indexed with a string to get a property value:

```lua
local instance = Instance.new("Workspace")
instance[sym.IsService] = true
print(instance[sym.IsService]) --> true

```

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [AttrConfig](#attrconfig) | Field | Gets the inherited [AttrConfig](type:AttrConfig) of an instance. |
| [Desc](#desc) | Field | Gets the inherited [descriptor](type:Desc) of an instance. |
| [IsService](#isservice) | Field | Determines whether an instance is a service. |
| [Metadata](#metadata) | Field | Gets the metadata of a [DataModel](type:DataModel). |
| [Properties](#properties) | Field | Gets the properties of an instance. |
| [RawAttrConfig](#rawattrconfig) | Field | Accesses the direct [AttrConfig](type:AttrConfig) of an instance. |
| [RawDesc](#rawdesc) | Field | Accesses the direct [descriptor](type:Desc) of an instance. |
| [Reference](#reference) | Field | Determines the value used to identify the instance. |

</div>

# Fields

----

## AttrConfig

 `sym.AttrConfig: Symbol [readonly]`

The **AttrConfig** symbol gets the inherited [AttrConfig](type:AttrConfig) of an instance.

## Desc

 `sym.Desc: Symbol [readonly]`

The **Desc** symbol gets the inherited [descriptor](type:Desc)
of an instance.

## IsService

 `sym.IsService: Symbol [readonly]`

The **IsService** symbol determines whether an instance is a service.

## Metadata

 `sym.Metadata: Symbol [readonly]`

The **Metadata** symbol gets the metadata of a [DataModel](type:DataModel).

## Properties

 `sym.Properties: Symbol [readonly]`

The **Properties** symbol gets the properties of an instance.

## RawAttrConfig

 `sym.RawAttrConfig: Symbol [readonly]`

The **RawAttrConfig** symbol accesses the direct [AttrConfig](type:AttrConfig) of an instance.

## RawDesc

 `sym.RawDesc: Symbol [readonly]`

The **RawDesc** symbol accesses the direct [descriptor](type:Desc) of an instance.

## Reference

 `sym.Reference: Symbol [readonly]`

The **Reference** symbol determines the value used to identify the
instance.