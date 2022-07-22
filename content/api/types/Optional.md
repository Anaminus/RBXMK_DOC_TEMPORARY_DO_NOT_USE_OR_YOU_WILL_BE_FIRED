+++
weight = 1
title = "Optional"
description = "An optional exprim of a type."
categories = ["API", "Type"]
+++

`type Optional = Optional`

The **Optional** type is an exprim that encapsulates another type, such
that the value is either present or not present.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [none](#none) | Constructor | An Optional with no value. |
| [some](#some) | Constructor | An Optional with some value. |

</div>

# Constructors

----

## none

 `Optional.none(type: string): Optional`

The **none** constructor returns an empty Optional exprim of the given
type.

```lua
model.WorldPivotData = Optional.none("CFrame") -- type is Optional<cframe>
print(typeof(model.WorldPivotData.Value)) --&gt; nil</cframe>
```

## some

 `Optional.some(value: Variant): Optional`

The **some** constructor returns an Optional exprim with the type of
*value*, that encapsulates *value*.

```lua
local value = CFrame.new(1,2,3)
model.WorldPivotData = Optional.some(value) -- type is Optional<cframe>
print(typeof(model.WorldPivotData.Value)) --&gt; CFrame</cframe>
```