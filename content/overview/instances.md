+++
weight = 10
title = "Instances"
+++

A major difference between Roblox and rbxmk is what an **instance** represents.
In Roblox, an instance is a live object that acts and reacts. In rbxmk, an
instance represents *data*, and only data.

Consider the RBXL file format. Files of this format contain information used to
reconstruct the instances that make up a place or model. Such files are static:
they contain only data, but are difficult to manipulate in-place. Instances in
rbxmk are like this, except that they are also interactive: the user can freely
modify data and move it around.

Because of this, there are several differences between the Roblox API and the
rbxmk API. By default, any kind of class can be created. Instances are just
data, including the class name. The [ClassName](api/types/Instance#ClassName)
property can even be assigned to.

```lua
local foobar = Instance.new("Foobar")
foobar.ClassName = "FizzBuzz" -- allowed
```

# Properties
Instances also have no defined properties by default. A value of any type can be
assigned to any property. Likewise, properties that are not explicitly assigned
effectively do not exist.

```lua
local part = Instance.new("Part")
part.Foobar = 42 -- allowed
print(part.Position) --> nil
```

That said, even though it is possible for rbxmk to create arbitrary classes with
arbitrary properties, this does not mean such instances will be interpreted in
any meaningful way when sent over to Roblox. The most convenient way to enforce
the correctness of instances is to use [descriptors](overview/descriptors).

Alternatively, the [rbxmk.get](api/libraries/rbxmk#get) and
[rbxmk.set](api/libraries/rbxmk#set) functions can be used to get and set
properties with type information defined manually.

```lua
local value = Instance.new("IntValue")
value.Value = 42 -- Set as double.
rbxmk.set(value, "Value", 42, "int") -- Set as int.
```

# Behaviors
{{<noimpl reason="Behavior descriptors">}}

In addition to getting and setting properties, rbxmk implements various
**behaviors** on instances. Many behaviors are applied to all instances, and
others depend on the class. Even though instances in rbxmk represent only data,
behaviors are made available to make certain tasks easier.

Through [behavior descriptors](/overview/descriptors#behaviors), all behaviors
are fully configurable by the user, to be applied to certain classes and fields,
or removed entirely. The [Behaviors](/overview/descriptors/behaviors) page lists
each behavior, and how they are configured by default. The [API reference page
on instances](/api/types/Instance) provides a complete reference for all
available behaviors.

## Essential methods
The methods for navigating instance trees are available on all instances, which
includes [Parent][Parent], [FindFirstChild][FindFirstChild],
[GetChildren][GetChildren], and so on.

Convenience methods like [Clone][Clone], [ClearAllChildren][ClearAllChildren],
[Destroy][Destroy], and [GetFullName][GetFullName] are implemented.

With descriptors specified, other methods like [IsA][IsA] and
[FindFirstChildWhichIsA][FindFirstChildWhichIsA] become fully functional.


[Parent]: /api/types/Instance#parent
[FindFirstChild]: /api/types/Instance#findfirstchild
[GetChildren]: /api/types/Instance#getchildren
[IsA]: /api/types/Instance#isa
[FindFirstChildWhichIsA]: /api/types/Instance#findfirstchildwhichisa
[Clone]: /api/types/Instance#clone
[ClearAllChildren]: /api/types/Instance#clearallchildren
[Destroy]: /api/types/Instance#destroy
[GetFullName]: /api/types/Instance#getfullname


## Child indexing
Another notable difference between Roblox and rbxmk is that children cannot be
directly indexed by name. Without a descriptor, *all* properties are considered
valid, so there would be no room to interpret an index as a child.

```lua
local tree = workspace.TreeModel
--> nil; property "TreeModel" has not been assigned to.
```

More generally, child indexing has been proven to have poor forward
compatibility. New properties are added to Roblox's API all the time, and every
such change has the potential to cause a script to break, because the script
expected a child and got the new property instead.

{{<noimpl reason="IndexChildren">}}
rbxmk moves past this problem by disabling child indexing by default. It can be
re-enabled with the [IndexChildren](overview/descriptors#indexchildren)
descriptor config. However, the [Instance.Descend](api/types/Instance#Descend)
method is introduced to provide a convenient and safe alternative.

## Attributes
Instances in Roblox and rbxmk have **attributes**, which are similar to custom
properties. Roblox serializes all attributes into a single property in a binary
format. In rbxmk, this is implemented by the [rbxattr
format](formats.md#user-content-rbxattr).

rbxmk provides the same API as Roblox for manipulating attributes:

- [GetAttribute](/api/types/Instance#getattribute)
- [GetAttributes](/api/types/Instance#getattributes)
- [SetAttribute](/api/types/Instance#setattribute)

Additionally, rbxmk provides the
[SetAttributes](/api/types/Instance#setattributes) method for setting all the
attributes of an instance more efficiently. Instead of decoding, updating, and
encoding the attributes property each time, this will set all attributes in one
go.

## Tags
{{<noimpl>}}

Instances also have **tags** which, like attributes, are serialized into a
single property. rbxmk provides the [rbxmk.tags](/api/libraries/rbxmk#tags)
object for managing the tags of all instances. In addition, an instance with the
CollectionService class will have methods that operate on the tags within the
tree that the instance is a part of:

- [AddTag](/api/types/Instance#addtag)
- [GetAllTags](/api/types/Instance#getalltags)
- [GetTagged](/api/types/Instance#gettagged)
- [GetTags](/api/types/Instance#gettags)
- [HasTag](/api/types/Instance#hastag)
- [RemoveTag](/api/types/Instance#removetag)

## Pivots
{{<noimpl>}}

The **pivots** feature of rbxmk comprises a number of features related to the
position and orientation of 3D objects. Principally, this is the
[GetPivot][GetPivot] and [PivotTo][PivotTo] methods, which allow entire models
to be moved around in 3D space.

Additionally, the [GetBoundingBox][GetBoundingBox],
[GetPrimaryPartCFrame][GetPrimaryPartCFrame], and
[SetPrimaryPartCFrame][SetPrimaryPartCFrame] methods are available on instances
with the Model class.

Moreover, rbxmk implements certain properties whose values are derived from
other properties. For example, on BaseParts, the [Position][Position] and
[Orientation][Orientation] are derived from the CFrame property.

[GetPivot]: /api/types/Instance#getpivot
[PivotTo]: /api/types/Instance#pivotto
[GetBoundingBox]: /api/types/Instance#getboundingbox
[GetPrimaryPartCFrame]: /api/types/Instance#getprimarypartcframe
[SetPrimaryPartCFrame]: /api/types/Instance#setprimarypartcframe
[Position]: /api/types/Instance#position
[Orientation]: /api/types/Instance#orientation
