+++
weight = 1
title = "Axes"
description = "A set of active axes."
categories = ["API", "Type"]
+++

The **Axes** type represents a set of orthogonal coordinate axes that are
considered active. Corresponds to the [Axes](https://developer.roblox.com/en-us/api-reference/datatype/Axes)
type in Roblox.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [fromComponents](#fromcomponents) | Constructor | Creates a new Axes with components set directly from each argument. |
| [new](#new) | Constructor | Creates a new Axes with components set from a number of values. |
| [Back](#back) | Property | Corresponds to the Z axes. |
| [Bottom](#bottom) | Property | Corresponds to the Y axes. |
| [Front](#front) | Property | Corresponds to the Z axes. |
| [Left](#left) | Property | Corresponds to the X axes. |
| [Right](#right) | Property | Corresponds to the X axes. |
| [Top](#top) | Property | Corresponds to the Y axes. |
| [X](#x) | Property | Whether the X axis is active. |
| [Y](#y) | Property | Whether the Y axis is active. |
| [Z](#z) | Property | Whether the Z axis is active. |
| [\_\_eq](#__eq) | Operator | Returns whether two Axes values are equal. |

</div>

# Constructors

----

## fromComponents

 `Axes.fromComponents(x: bool, y: bool, z: bool)`

The **fromComponents** constructor returns a new Axes value, with each
argument setting the corresponding component.

## new

 `Axes.new(...: EnumItem | string | int)`

The **new** constructor returns a new Axes value. Each valid argument sets
a component of the value, depending on the type:

- EnumItem:
  - Enum name is `"Axis"`, and item name is `"X"`,
    `"Y"`, or `"Z"`.
  - Enum name is `"NormalId"`, and item name is one of the following:

    - `"Right"`, `"Left"`: sets X.
    - `"Top"`, `"Bottom"`: sets Y.
    - `"Back"`, `"Front"`: sets Z.
- number: value is one of the following:
  - `0`: sets X.
  - `1`: sets Y.
  - `2`: sets Z.
- string: value is `"X"`, `"Y"`, or
  `"Z"`.

# Properties

----

## Back

 `Axes.Back: bool [readonly]`

The **Back** field returns whether the Z axis is active.

## Bottom

 `Axes.Bottom: bool [readonly]`

The **Bottom** field returns whether the Y axis is active.

## Front

 `Axes.Front: bool [readonly]`

The **Front** field returns whether the Z axis is active.

## Left

 `Axes.Left: bool [readonly]`

The **Left** field returns whether the X axis is active.

## Right

 `Axes.Right: bool [readonly]`

The **Right** field returns whether the X axis is active.

## Top

 `Axes.Top: bool [readonly]`

The **Top** field returns whether the Y axis is active.

## X

 `Axes.X: bool [readonly]`

The **X** field returns whether the X axis is active.

## Y

 `Axes.Y: bool [readonly]`

The **Y** field returns whether the Y axis is active.

## Z

 `Axes.Z: bool [readonly]`

The **Z** field returns whether the Z axis is active.

# Operators

----

## \_\_eq

 `Axes == Axes`

The **equal** operator returns true if both operands are Axes, and each
corresponding component is equal.