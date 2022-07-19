+++
weight = 102
title = "roblox"
+++

The Roblox library contains an environment similar to the Roblox Lua API. It
is included directly into the global environment.

| Item | Kind | Description |
| --- | --- | --- |
| [typeof](#typeof) | Function | Gets the internal type of a userdata. |

# Functions

----

## typeof

 `typeof(value: any): string`

The **typeof** function returns the type of a value. For userdata, the
internal value is returned. Other Lua values return the same as the type
function.