+++
weight = 10
title = "Instances"
+++

A major difference between Roblox and rbxmk is what an instance represents. In
Roblox, an instance is a live object that acts and reacts. In rbxmk, an instance
represents *data*, and only data.

Consider the RBXL file format. Files of this format contain information used to
reconstruct the instances that make up a place or model. Such files are static:
they contain only data, but are difficult to manipulate in-place. Instances in
rbxmk are like this, except that they are also interactive: the user can freely
modify data and move it around.

Because of this, there are several differences between the Roblox API and the
rbxmk API. By default, any kind of class can be created. Instances are just
data, including the class name. The ClassName property can even be assigned to.

```lua
local foobar = Instance.new("Foobar")
foobar.ClassName = "FizzBuzz" -- allowed
```

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
the correctness of instances is to use [descriptors][descriptors].

Another notable difference is that children cannot be indexed by name directly.
Without a descriptor, *all* properties are considered valid, so no there would
be no room to interpret an index as a child.

More generally, child indexing has been proven to have poor forward
compatibility. New properties are added to the API all the time, and every such
change has the potential to cause a script to break, because the script expected
a child and got a new property instead.

rbxmk moves past this problem by simply not implementing child indexing.
Instead, the [Instance.Descend][Instance.Descend] method is introduced to
provide a convenient and safe alternative.

# Attributes
[Attributes]: #user-content-attributes

Instances in Roblox and rbxmk have **attributes**, which are similar to custom
properties.

Roblox serializes all attributes into a single property in a binary format. In
rbxmk, this format is implemented by the [rbxattr
format](formats.md#user-content-rbxattr).

rbxmk provides the same API as Roblox for manipulating attributes:

- [Instance.GetAttribute](types.md#user-content-instancegetattribute)
- [Instance.GetAttributes](types.md#user-content-instancegetattributes)
- [Instance.SetAttribute](types.md#user-content-instancesetattribute)

Additionally, rbxmk provides the
[SetAttributes](types.md#user-content-instancesetattributes) method for setting
all the attributes of an instance more efficiently.

In order to maintain rbxmk's theme of forward-compatibility, rbxmk provides the
[AttrConfig][AttrConfig] type to configure how attributes are applied to an
instance. AttrConfigs are inherited, the behavior of which is described on the
[Value inheritance][value-inheritance] page.
