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

However, most of the time, the user will be using rbxmk to manipulate values
specifically for Roblox. It's often less convenient for the user to specify type
information manually; the API is slightly off from that of Roblox, therefore
being less familiar. It would be great if this type information could be defined
and enforced automatically.

The solution to this is **descriptors**. A descriptor contains information about
what classes exist, the properties that exist on each class, what enums are
defined, and so on.

The primary descriptor type is the [**RootDesc**][RootDesc]. This contains a
complete description of the classes and enums of an entire API.

An [Instance][Instance] can have a RootDesc assigned to it. This state is
inherited by any descendant instances. See [sym.Desc][Instance.sym.Desc] for
more information.

Additionally, the [rbxmk.globalDesc][rbxmk.globalDesc] field may be used to
apply a RootDesc globally. When globalDesc is set, any instance that wouldn't
otherwise inherit a descriptor will use this global descriptor.

When an instance has a descriptor, several behaviors are enforced:

- When the global descriptor is set,
  [Instance.new](types.md#user-content-instancenew) errors if the given class
  name does not exist (Instance.new can also receive a descriptor).
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
  [DataModel.GetService](types.md#user-content-datamodelgetservice) must have
  the "Service" tag.

A RootDesc has methods to get and set information on the fly. Descriptors for a
particular API element are represented by a dictionary that contains the fields
of the element. The following types are related:

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
[RootDesc][RootDesc]           | Describes an entire API.
[TypeDesc][TypeDesc]           | Describes the type of a value.

# Diffing and Patching
[diffing-and-patching]: #user-content-diffing-and-patching

Descriptors can be compared and patched with the
[RootDesc.Diff](types.md#user-content-rootdescdiff) and
[RootDesc.Patch](types.md#user-content-rootdescpatch) methods. Diff returns a
list of [**DescActions**](types.md#user-content-descaction), which describe how
to transform the first descriptor into the second. Patch can used to apply this
transformation.

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

The [dump.desc-patch.json][dumpPatch] file can be used to patch Roblox's API
dump to include missing items. This aids in proper conversion of binary formats
to XML formats.

[dumpPatch]: examples/dump-patch
