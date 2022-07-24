+++
weight = 1
title = "Vector2int16"
description = "A two-dimensional Euclidean vector with 16-bit integer precision."
categories = ["API", "Type"]
+++

The **Vector2int16** type represents a two-dimensional Euclidean vector
with 16-bit integer precision.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns the zero vector. Returns a vector composed by each given coordinate. |
| [X](#x) | Property | The X coordinate. |
| [Y](#y) | Property | The Y coordinate. |
| [\_\_add](#__add) | Operator | The sum of two vectors. |
| [\_\_div](#__div) | Operator | Divides each corresponding component. Divides each component. |
| [\_\_eq](#__eq) | Operator | Returns whether two Vector2int16 values are equal. |
| [\_\_mul](#__mul) | Operator | Multiplies each corresponding component. Multiplies each component. |
| [\_\_sub](#__sub) | Operator | The difference between two vectors. |
| [\_\_unm](#__unm) | Operator | The negation of the vector. |

</div>

# Constructors

----

## new

 `Vector2int16.new(): Vector2int16`

The **new** constructor returns the origin vector, where each coordinate
is 0.

 `Vector2int16.new(x: int, y: int): Vector2int16`

The **new** constructor returns a vector composed by each given
component.

# Properties

----

## X

 `Vector2int16.X: int [readonly]`

The **X** field returns the X coordinate of the vector.

## Y

 `Vector2int16.Y: int [readonly]`

The **Y** field returns the Y coordinate of the vector.

# Operators

----

## \_\_add

 `Vector2int16 + Vector2int16 -> Vector2int16`

The **add** operator returns a vector where each corresponding component
of the two operands are summed.

## \_\_div

 `Vector2int16 / Vector2int16 -> Vector2int16`

The **div** operator returns a vector where each corresponding component
of the two operands are divided.

 `Vector2int16 / Number -> Vector2int16`

The **div** operator returns a vector where each component of the first
operand is divided by the second operand.

## \_\_eq

 `Vector2int16 == Vector2int16`

The **equal** operator returns true if both operands are Vector2int16, and
each corresponding component is equal.

## \_\_mul

 `Vector2int16 * Vector2int16 -> Vector2int16`

The **mul** operator returns a vector where each corresponding component
of the two operands are multiplied.

 `Vector2int16 * Number -> Vector2int16`

The **mul** operator returns a vector where each component of the first
operand is multiplied by the second operand.

## \_\_sub

 `Vector2int16 - Vector2int16 -> Vector2int16`

The **sub** operator returns a vector where each corresponding component
of the two operands are subtracted.

## \_\_unm

 `-Vector2int16 -> Vector2int16`

The **unm** operator returns a vector where each component is negated.