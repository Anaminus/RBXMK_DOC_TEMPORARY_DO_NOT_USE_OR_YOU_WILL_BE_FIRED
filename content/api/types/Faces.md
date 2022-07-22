+++
weight = 1
title = "Faces"
description = "A set of active directions."
categories = ["API", "Type"]
+++

The **Faces** type represents a set of directions, on three orthogonal
axes, that are considered active. Corresponds to the [Faces](https://developer.roblox.com/en-us/api-reference/datatype/Faces)
type in Roblox.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [fromComponents](#fromcomponents) | Constructor | Creates a new Faces with components set directly from each argument. |
| [new](#new) | Constructor | Creates a new Faces with components set from a number of values. |
| [Back](#back) | Property | Whether the back face is active. |
| [Bottom](#bottom) | Property | Whether the bottom face is active. |
| [Front](#front) | Property | Whether the front face is active. |
| [Left](#left) | Property | Whether the left face is active. |
| [Right](#right) | Property | Whether the right face is active. |
| [Top](#top) | Property | Whether the top face is active. |
| [\_\_eq](#__eq) | Operator | Returns whether two Faces values are equal. |

</div>

# Constructors

----

## fromComponents

 `Faces.fromComponents(right: bool, top: bool, back: bool, left: bool, bottom: bool, front: bool)`

The **fromComponents** constructor returns a new Faces value, with each
argument setting the corresponding component.

## new

 `Faces.new(...: EnumItem | string | int)`

The **new** constructor returns a new Faces value. Each valid argument
sets a component of the value, depending on the type:

- EnumItem:
  - Enum name is `"Axis"`, and item name is one of the following:

    - `"X"`: sets Right and Left.
    - `"Y"`: sets Top and Bottom.
    - `"Z"`: sets Back and Front.
  - Enum name is `"NormalId"`, and item name is `"Right"`,
    `"Top"`, `"Back"`, `"Left"`,
    `"Bottom"`, or `"Front"`.
- number: value is one of the following:
  - `0`: sets Right.
  - `1`: sets Top.
  - `2`: sets Back.
  - `3`: sets Left.
  - `4`: sets Bottom.
  - `5`: sets Front.
- string: value is `"Right"`, `"Top"`,
  `"Back"`, `"Left"`, `"Bottom"`, or
  `"Front"`.

# Properties

----

## Back

 `Faces.Back: bool [readonly]`

The **Back** field returns whether the back face is active.

## Bottom

 `Faces.Bottom: bool [readonly]`

The **Bottom** field returns whether the bottom face is active.

## Front

 `Faces.Front: bool [readonly]`

The **Front** field returns whether the front face is active.

## Left

 `Faces.Left: bool [readonly]`

The **Left** field returns whether the left face is active.

## Right

 `Faces.Right: bool [readonly]`

The **Right** field returns whether the right face is active.

## Top

 `Faces.Top: bool [readonly]`

The **Top** field returns whether the top face is active.

# Operators

----

## \_\_eq

 `Faces == Faces`

The **equal** operator returns true if both operands are Faces, and each
corresponding component is equal.