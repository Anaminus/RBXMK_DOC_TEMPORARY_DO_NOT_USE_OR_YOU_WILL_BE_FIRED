+++
weight = 30
title = "Value inheritance"
+++

Certain symbol fields on [Instances][Instance] have an inheritance behavior.

Member                                    | Principal type           | Raw member                                      | Global field
------------------------------------------|--------------------------|-------------------------------------------------|-------------
[sym.AttrConfig][Instance.sym.AttrConfig] | [AttrConfig][AttrConfig] | [sym.RawAttrConfig][Instance.sym.RawAttrConfig] | [rbxmk.globalAttrConfig][rbxmk.globalAttrConfig]
[sym.Desc][Instance.sym.Desc]             | [RootDesc][RootDesc]     | [sym.RawDesc][Instance.sym.RawDesc]             | [rbxmk.globalDesc][rbxmk.globalDesc]

The following sections describe the aspects of this behavior for each member.

# Indexing
The member has a **principal type**, which indicates the type of the main value
assigned to the member.

Getting the member will return either a value of the principal type, or nil. If
the instance has no value, then each ancestor of the instance is searched until
a value is found. If none are still found, then the global value is returned. If
there is no global value, then nil is finally returned.

When setting the member, the value can be of the principal type, false, or nil.
Setting to the member sets the value only for the current instance.

- Setting to a value of the principal type will set the value directly for the
  current instance, which may be inherited.
- Setting to nil will cause the instance to have no direct value, and the value
  will be inherited instead.
- Setting to false will "block" inheritance, forcing the instance to have no
  value. This behaves sort of like a value that is empty; the instance wont
  inherit any other values, and this blocked state can be inherited.

# Raw member
The member has a corresponding **raw member**, which gets the value directly.
Getting the raw member will return the value if the instance has a value
assigned, false if the member is blocked, or nil if no value is assigned.
Setting the raw member behaves the same as setting the corresponding member.

# Global field
The member has a corresponding **global field** in the [rbxmk
library](libraries.md#user-content-rbxmk), which sets a global value to be
applied to any instance that would otherwise inherit nothing.
