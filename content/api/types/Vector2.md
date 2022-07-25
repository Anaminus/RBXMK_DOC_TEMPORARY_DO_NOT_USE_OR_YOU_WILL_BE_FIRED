+++
weight = 1
title = "Vector2"
description = "A two-dimensional Euclidean vector."
categories = ["API", "Type"]
+++

The **Vector2** type represents a two-dimensional Euclidean vector.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns the zero vector. Returns a vector composed by each given coordinate. |
| [Magnitude](#magnitude) | Property | The length of the vector. |
| [Unit](#unit) | Property | The direction of the vector. |
| [X](#x) | Property | The X coordinate. |
| [Y](#y) | Property | The Y coordinate. |
| [Cross](#cross) | Method | Returns the cross product of two vectors. |
| [Dot](#dot) | Method | Returns the dot product of two vectors. |
| [Lerp](#lerp) | Method | Linearly interpolates between two vectors. |
| [\_\_add](#__add) | Operator | The sum of two vectors. |
| [\_\_div](#__div) | Operator | Divides each corresponding component. Divides each component. |
| [\_\_eq](#__eq) | Operator | Returns whether two Vector2 values are equal. |
| [\_\_mul](#__mul) | Operator | Multiplies each corresponding component. Multiplies each component. |
| [\_\_sub](#__sub) | Operator | The difference between two vectors. |
| [\_\_unm](#__unm) | Operator | The negation of the vector. |

</div>

# Constructors

----

## new

 `Vector2.new(): Vector2`

The **new** constructor returns the origin vector, where each coordinate
is 0.

 `Vector2.new(x: float, y: float): Vector2`

The **new** constructor returns a vector composed by each given
component.

# Properties

----

## Magnitude

 `Vector2.Magnitude: float [readonly]`

The **Magnitude** field returns the length of the vector.

## Unit

 `Vector2.Unit: Vector2 [readonly]`

The **Unit** field returns a vector with the same direction, but a length
of 1.

## X

 `Vector2.X: float [readonly]`

The **X** field returns the X coordinate of the vector.

## Y

 `Vector2.Y: float [readonly]`

The **Y** field returns the Y coordinate of the vector.

# Methods

----

## Cross

 `Vector2:Cross(op: Vector2): float`

The **Cross** method returns the cross product of the vector and *op*
extended into three dimensions with Z coordinates of 0.

## Dot

 `Vector2:Dot(op: Vector2): float`

The **Dot** method returns the dot product of the vector and
*op*.

## Lerp

 `Vector2:Lerp(goal: Vector2, alpha: float): Vector2`

The **Lerp** method returns a vector linearly interpolated from the vector
to *goal* according to *alpha*, which has an interval of \[0, 1\].

# Operators

----

## \_\_add

 `Vector2 + Vector2 -> Vector2`

The **add** operator returns a vector where each corresponding component
of the two operands are summed.

## \_\_div

 `Vector2 / Vector2 -> Vector2`

The **div** operator returns a vector where each corresponding component
of the two operands are divided.

 `Vector2 / number -> Vector2`

The **div** operator returns a vector where each component of the first
operand is divided by the second operand.

## \_\_eq

 `Vector2 == Vector2`

The **equal** operator returns true if both operands are Vector2, and each
corresponding component is equal.

## \_\_mul

 `Vector2 * Vector2 -> Vector2`

The **mul** operator returns a vector where each corresponding component
of the two operands are multiplied.

 `Vector2 * number -> Vector2`

The **mul** operator returns a vector where each component of the first
operand is multiplied by the second operand.

## \_\_sub

 `Vector2 - Vector2 -> Vector2`

The **sub** operator returns a vector where each corresponding component
of the two operands are subtracted.

## \_\_unm

 `-Vector2 -> Vector2`

The **unm** operator returns a vector where each component is negated.