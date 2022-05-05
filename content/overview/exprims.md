+++
weight = 40
title = "Explicit primitives"
+++

The properties of instances in Roblox have a number of different types. Many of
these types can be expressed in Lua through constructors. Examples of such are
CFrame, Vector3, UDim2, and so on. These types correspond to internal data types
within the Roblox engine. The Lua representation of, say, a CFrame, is a
userdata with accessible fields.

Some Roblox types are represented with a simple Lua primitive, such as a number
or string. For example, the Roblox types `int`, `int64`, `float`, and `double`
all map to Lua's `number` type. When setting a property, the engine is able to
reflect this Lua `number` back to the correct Roblox type, because the property
has a descriptor that includes the property's type.

In rbxmk, when an instance has a descriptor, it is able to make this conversion
as expected. However, the user may not always have access to descriptors. When
no descriptors are specified, properties have no types. For example, when a
property is set to a Lua number, it is always converted into a `double`. In the
absence of extra type information, the user needs some way to set specific
Roblox types.

This problem can be solved with "explicit primitives", or **exprims**. An exprim
is a userdata representation of an otherwise ambiguous type. This userdata
carries type metadata along with a given value, allowing the value to be mapped
to the correct Roblox type when it is set as a property.

The [types library](libraries.md#user-content-types) contains a constructor
function for each exprim type.

```lua
-- Problem
local v = Instance.new("IntValue")
v.Name = "Value"
v.Value = 42 -- type is `double`; not correct for IntValue.

-- Solution
local v = Instance.new("IntValue")
v.Name = "Value"
v.Value = types.int64(42) -- Type is int64.
```

The default Roblox type that maps to Lua strings is `string`. As such, `string`
has no exprim. Likewise, the default type that maps to Lua numbers is `double`,
so it also has no exprim.

An exprim userdata has no fields or operators other than the "Value" field,
which returns the underlying primitive value:

```lua
v.Value = types.int64(v.Value.Value + 1)
```

Exprims are meant to be short-lived, and shouldn't really be used beyond getting
or setting a property in the absence of [descriptors][descriptors]. When
possible, descriptors should be utilized instead.
