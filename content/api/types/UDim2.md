+++
weight = 1
title = "UDim2"
description = "A UDim on two dimensions."
categories = ["API", "Type"]
+++

The **UDim2** type represents a UDim on two dimensions.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [fromOffset](#fromoffset) | Constructor | Returns a UDim2 from offset components. |
| [fromScale](#fromscale) | Constructor | Returns a UDim2 from scale components. |
| [new](#new) | Constructor | Returns a UDim2 from components. Returns a UDim2 from UDims. |
| [Height](#height) | Property | The height of the UDim2. |
| [Width](#width) | Property | The width of the UDim2. |
| [X](#x) | Property | The X dimension. |
| [Y](#y) | Property | The Y dimension. |
| [Lerp](#lerp) | Method | Lineearly interpolates between two UDim2 values. |
| [\_\_add](#__add) | Operator | The sum of two UDim2 values. |
| [\_\_eq](#__eq) | Operator | Returns whether two UDim2 values are equal. |
| [\_\_sub](#__sub) | Operator | The difference between two UDim values. |
| [\_\_unm](#__unm) | Operator | The negation of the UDim2. |

</div>

# Constructors

----

## fromOffset

 `UDim2.fromOffset(x: int, y: int): UDim2`

The **fromOffset** constructor returns a UDim2 that sets the offset
components of each dimension.

## fromScale

 `UDim2.fromScale(x: float, y: float): UDim2`

The **fromScale** constructor returns a UDim2 that sets the scale
components of each dimension.

## new

 `UDim2.new(xScale: float, xOffset: int, yScale: float, yOffset: int): UDim2`

The **new** constructor returns a UDim2 composed from the components of
each UDim.

 `UDim2.new(x: UDim, y: UDim): UDim2`

The **new** constructor returns a UDim2 composed from two UDim values.

# Properties

----

## Height

 `UDim2.Height: UDim [readonly]`

The **Height** field returns the Y dimension of the UDim2.

## Width

 `UDim2.Width: UDim [readonly]`

The **Width** field returns the X dimension of the UDim2.

## X

 `UDim2.X: UDim [readonly]`

The **X** field returns the X dimension of the UDim2.

## Y

 `UDim2.Y: UDim [readonly]`

The **Y** field returns the Y dimension of the UDim2.

# Methods

----

## Lerp

 `UDim2:Lerp(goal: UDim2, alpha: float): UDim2`

The **Lerp** method returns a UDim2 linearly interpolated from the UDim2
to *goal* according to *alpha*, which has an interval of \[0, 1\].

# Operators

----

## \_\_add

 `UDim2 + UDim2 = UDim2`

The **add** operator returns a UDim2 where each corresponding component of
the two operands are summed.

## \_\_eq

 `UDim2 == UDim2`

The **equal** operator returns true if both operands are UDim2, and each
corresponding component is equal.

## \_\_sub

 `UDim2 - UDim2 = UDim2`

The **sub** operator returns a UDim2 where each corresponding component of
the two operands are subtracted.

## \_\_unm

 `-UDim2 = UDim2`

The **unm** operator returns a UDim2 where each component is negated.