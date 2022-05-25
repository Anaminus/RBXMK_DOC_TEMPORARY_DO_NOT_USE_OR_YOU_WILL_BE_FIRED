+++
weight = 20
title = "Descriptors"
+++

By default, rbxmk has no knowledge of the classes, members, and enums that are
defined by Roblox. As such, instances can be of any class, properties can be of
any type, and there are no constant enum values. By not explicitly requiring
such information, rbxmk can remain relatively forward-compatible with future
updates to Roblox. It also allows the user to construct values outside the
constraints of the Roblox API.

However, most of the time, the user will be using rbxmk to process values
specifically for Roblox. It's often less convenient for the user to specify type
information manually; the API is different from that of Roblox, and is therefore
less familiar. It would be great if this type information could be defined and
enforced automatically.

The solution to this is **descriptors**. A descriptor contains information about
what classes exist, the properties that exist on each class, what enums are
defined, and so on.

# Desc objects
The [**Desc**](/api/types/Desc) type represents the set of descriptors for an
API. This contains a complete description of the classes and enums of an entire
API, as well as supplementary information.

An [Instance](/api/types/Instance) can have a Desc assigned to it, and this
state will be inherited by any descendant instances. See
[sym.Desc](/api/types/Instance#sym.Desc) for more information.

Additionally, the [rbxmk.globalDesc](/api/libraries/rbxmk#globalDesc)
field may be used to apply a Desc globally. When globalDesc is set, any instance
that wouldn't otherwise inherit a descriptor will use this global descriptor.

When an instance has a descriptor, several behaviors are enforced:

- When the global descriptor is set, [Instance.new](/api/types/Instance#new)
  errors if the given class name does not exist.
- A property will throw an error if it does not exist for the class.
- Getting an uninitialized property will throw an error.
- Getting a property that currently has an incorrect type will throw an error.
- Setting a property to a value of the incorrect type will throw an error.
- A property of the "Class" type category will throw an error if the assigned
  value is not an instance of the expected class.
- The value assigned to a property of the "Enum" type category will be coerced
  into a token. The value can be an enum item of the expected enum, or a number
  or string of the correct value.
- The class of an instance created from
  [GetService](/overview/descriptors/behaviors#ServiceProvider.GetService) must
  have the "Service" tag.

The Desc type has methods to get and set information on the fly. Descriptors for
a particular API element are represented by a dictionary that contains the
fields of the element. The following types are related:

Type                           | Description
-------------------------------|------------
[CallbackDesc][CallbackDesc]   | Describes a callback class member.
[ClassDesc][ClassDesc]         | Describes a class.
[EnumDesc][EnumDesc]           | Describes an enum.
[EnumItemDesc][EnumItemDesc]   | Describes an enum item.
[EventDesc][EventDesc]         | Describes an event class member.
[FunctionDesc][FunctionDesc]   | Describes a function class member.
[MemberDesc][MemberDesc]       | A sum of the defined member types.
[ParameterDesc][ParameterDesc] | Describes a parameter of a function, event, or callback.
[PropertyDesc][PropertyDesc]   | Describes a property class member.
[TypeDesc][TypeDesc]           | Describes the type of a value.

[CallbackDesc]: /api/types/CallbackDesc
[ClassDesc]: /api/types/ClassDesc
[Desc]: /api/types/Desc
[EnumDesc]: /api/types/EnumDesc
[EnumItemDesc]: /api/types/EnumItemDesc
[EventDesc]: /api/types/EventDesc
[FunctionDesc]: /api/types/FunctionDesc
[MemberDesc]: /api/types/MemberDesc
[ParameterDesc]: /api/types/ParameterDesc
[PropertyDesc]: /api/types/PropertyDesc
[TypeDesc]: /api/types/TypeDesc

# Diffing and Patching
Descriptors can be compared and patched with the
[Desc.Diff](/api/types/Desc#Diff) and [Desc.Patch](/api/types/Desc#Patch)
methods. Diff returns a list of [**DescAction**](/api/types/DescAction) values,
which describe how to transform the first descriptor into the second. Patch can
be used to apply this transformation.

```lua
-- List differences.
local diff = prevDesc:Diff(nextDesc)
-- Transform prev into next.
prevDesc:Patch(diff)
```

Patching is used primarily to augment some pregenerated descriptor with elements
that aren't present. For example, Roblox's API dump does not include the
`BinaryStringValue.Value` member. This can be patched with an action that adds
the member, allowing it to be used as normal.

More generally, patching allows any version of an API dump to be used, while
maintaining a separate, constant set of additional API elements.

The [dump.desc-patch.json][dumpPatch] file is a handcrafted patch to Roblox's
API dump that includes missing items. This aids in proper conversion of binary
formats to XML formats.

[dumpPatch]: https://github.com/Anaminus/rbxmk/tree/imperative/doc/examples/dump-patch

# Auxiliary data
{{<noimpl>}}

The descriptor data format is based off of the format of Roblox's API dump,
which enables API dumps to be used directly as descriptors. However, these dumps
paint an incomplete picture of the API.

rbxmk allows descriptors to include supplementary information. This comes in the
form of fields that have the `$rbxmk` prefix. They are kept separate to ensure
forward-compatibility with the API dump format.

## Extensions
{{<noimpl>}}
{{<goto page="extensions">}}List of extensions{{</goto>}}

Descriptor extensions directly augment elements in the base format with
additional data. Extensions are specified under the `$rbxmkExtensions` field.

{{<alert>}}While extensions can be specified by the user, rbxmk reserves all
extension names to define and use for its own functionality. For customized use
of extensions, it is recommended that the name be namespaced to avoid conflicts
with rbxmk and with other scripts. For example, instead of using "Attributes",
try "yourname_Attributes".{{</alert>}}

The [Extensions](extensions) page lists and describes the extensions implemented
by rbxmk.

## Configs
{{<noimpl>}}
{{<goto page="configs">}}List of configs{{</goto>}}

Descriptor configurations are similar to extensions, except that the data does
not have to be bound to any particular element. Configs are specified under the
`$rbxmkConfig` field.

{{<alert>}}While any config can be specified by the user, rbxmk reserves all
config names to define and use for its own functionality. For customized use of
configs, it is recommended that the name be namespaced to avoid conflicts with
rbxmk and with other scripts. For example, instead of using "BrickColors", try
"yourname_BrickColors".{{</alert>}}

The [Configurations](configurations) page lists and describes the configs
implemented by rbxmk.

## Behaviors
{{<noimpl>}}
{{<goto page="behaviors">}}List of behaviors{{</goto>}}

The base functionality of the [Instance](/api/types/Instance) type is to get and
set properties. rbxmk extends instances with additional behaviors based on the
class of the instance and the indexed field. In the interest of forward
compatibilty, which behaviors apply to a class and field can be reconfigured by
behavior descriptors.

Behaviors are specified under the `$rbxmkBehavior` field, which is an object
with the following fields:

Field   | Type   | Description
--------|--------|------------
Classes | object | Maps class names to behavior definitions.

A behavior definition is an object with the following fields:

Field       | Type   | Description
------------|--------|------------
Inheritable | bool   | Whether the behavior definition also applies to subclasses of the mapped class. Defaults to true.
Behaviors   | object | Map of field names to behaviors.

In the Behaviors map, each key is the name of a field that indexes an instance
of the mapped class. The field need not exist, or have a corresponding
descriptor. Including the "sym." prefix requires the field to be a symbol
instead of a string. Each value is the name of a predefined behavior. The
[Behaviors](overview/descriptors/behaviors) page lists and describes each
behavior implemented by rbxmk.

### Examples
The following descriptor will redefine attributes to be stored in the "Foobar"
property instead of the default "AttributesSerialize":

```json
{
	"$rbxmkBehavior": {
		"Classes": {
			"Instance": {
				"Behaviors": {
					"Foobar": "Instance.AttributesSerialize"
				}
			}
		}
	}
}
```

The following descriptor will remove the Descend method from instances:

```json
{
	"$rbxmkBehavior": {
		"Classes": {
			"Instance": {
				"Behaviors": {
					"Descend": ""
				}
			}
		}
	}
}
```

The following descriptor will cause the "Foobar" class to be used as the service
for managing tags instead of CollectionService:

```json
{
	"$rbxmkBehavior": {
		"Classes": {
			"CollectionService": {
				"AddTag": "",
				"GetAllTags": "",
				"GetTagged": "",
				"GetTags": "",
				"HasTag": "",
				"RemoveTag": ""
			},
			"Foobar": {
				"AddTag": "CollectionService.AddTag",
				"GetAllTags": "CollectionService.GetAllTags",
				"GetTagged": "CollectionService.GetTagged",
				"GetTags": "CollectionService.GetTags",
				"HasTag": "CollectionService.HasTag",
				"RemoveTag": "CollectionService.RemoveTag"
			}
		}
	}
}
```

The following descriptor describes how all behaviors are applied by default:

```json
{
	"$rbxmkBehavior": {
		"Classes": {
			"Instance": {
				"Behaviors": {
					"Name": "Instance.Name",
					"Parent": "Instance.Parent",
					"ClearAllChildren": "Instance.ClearAllChildren",
					"Clone": "Instance.Clone",
					"Destroy": "Instance.Destroy",
					"FindFirstAncestor": "Instance.FindFirstAncestor",
					"FindFirstAncestorOfClass": "Instance.FindFirstAncestorOfClass",
					"FindFirstAncestorWhichIsA": "Instance.FindFirstAncestorWhichIsA",
					"FindFirstChild": "Instance.FindFirstChild",
					"FindFirstChildOfClass": "Instance.FindFirstChildOfClass",
					"FindFirstChildWhichIsA": "Instance.FindFirstChildWhichIsA",
					"GetChildren": "Instance.GetChildren",
					"GetDescendants": "Instance.GetDescendants",
					"GetFullName": "Instance.GetFullName",
					"IsA": "Instance.IsA",
					"IsAncestorOf": "Instance.IsAncestorOf",
					"IsDescendantOf": "Instance.IsDescendantOf",

					"Descend": "rbxmk.Descend",

					"sym.Desc": "rbxmk.Desc",
					"sym.IsService": "rbxmk.IsService",
					"sym.Properties": "rbxmk.Properties",
					"sym.RawDesc": "rbxmk.RawDesc",
					"sym.Reference": "rbxmk.Reference",

					"AttributesSerialize": "Instance.AttributesSerialize",
					"GetAttribute": "Instance.GetAttribute",
					"GetAttributes": "Instance.GetAttributes",
					"SetAttribute": "Instance.SetAttribute",
					"SetAttributes": "Instance.SetAttributes",

					"Tags": "Instance.Tags",
				}
			},
			"DataModel": {
				"Behaviors": {
					"GetService": "ServiceProvider.GetService",
					"sym.Metadata": "rbxmk.Metadata"
				}
			},
			"CollectionService": {
				"AddTag": "CollectionService.AddTag",
				"GetAllTags": "CollectionService.GetAllTags",
				"GetTagged": "CollectionService.GetTagged",
				"GetTags": "CollectionService.GetTags",
				"HasTag": "CollectionService.HasTag",
				"RemoveTag": "CollectionService.RemoveTag"
			},
			"PVInstance": {
				"Behaviors": {
					"GetPivot": "PVInstance.GetPivot",
					"PivotTo": "PVInstance.PivotTo"
				}
			},
			"Model": {
				"Behaviors": {
					"WorldPivotData": "Model.WorldPivotData",
					"WorldPivot": "Model.WorldPivot",
					"PrimaryPart": "Model.PrimaryPart",
					"GetPrimaryPartCFrame": "Model.GetPrimaryPartCFrame",
					"SetPrimaryPartCFrame": "Model.SetPrimaryPartCFrame",
					"GetBoundingBox": "Model.GetBoundingBox"
				}
			},
			"BasePart": {
				"Behaviors": {
					"CFrame": "BasePart.CFrame",
					"Orientation": "BasePart.Orientation",
					"Position": "BasePart.Position",
					"Rotation": "BasePart.Rotation",
					"Size": "BasePart.Size"
				}
			},
			"Attachment": {
				"Behaviors": {
					"CFrame": "Attachment.CFrame",
					"Axis": "Attachment.Axis",
					"Orientation": "Attachment.Orientation",
					"Position": "Attachment.Position",
					"SecondaryAxis": "Attachment.SecondaryAxis",
					"WorldAxis": "Attachment.WorldAxis",
					"WorldCFrame": "Attachment.WorldCFrame",
					"WorldOrientation": "Attachment.WorldOrientation",
					"WorldPosition": "Attachment.WorldPosition",
					"WorldSecondaryAxis": "Attachment.WorldSecondaryAxis"
				}
			},
			"Bone": {
				"Behaviors": {
					"Transform": "Bone.Transform",
					"TransformedCFrame": "Bone.TransformedCFrame",
					"TransformedWorldCFrame": "Bone.TransformedWorldCFrame"
				}
			},
		}
	}
}
```
