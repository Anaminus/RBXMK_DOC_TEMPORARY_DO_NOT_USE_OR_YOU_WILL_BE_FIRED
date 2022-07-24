+++
weight = 1
title = "Vector3"
description = "A three-dimensional Euclidean vector."
categories = ["API", "Type"]
+++

The **Vector3** type represents a three-dimensional Euclidean vector.

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
| [Z](#z) | Property | The Z coordinate. |
| [Cross](#cross) | Method | Returns the cross product of two vectors. |
| [Dot](#dot) | Method | Returns the dot product of two vectors. |
| [FuzzyEq](#fuzzyeq) | Method | Returns whether two vectors are approximately equal. |
| [Lerp](#lerp) | Method | Linearly interpolates between two vectors. |
| [\_\_add](#__add) | Operator | The sum of two vectors. |
| [\_\_div](#__div) | Operator | Divides each corresponding component. Divides each component. |
| [\_\_eq](#__eq) | Operator | Returns whether two Vector3 values are equal. |
| [\_\_mul](#__mul) | Operator | Multiplies each corresponding component. Multiplies each component. |
| [\_\_sub](#__sub) | Operator | The difference between two vectors. |
| [\_\_unm](#__unm) | Operator | The negation of the vector. |

</div>

# Constructors

----

## new

 `Vector3.new(): Vector3`

The **new** constructor returns the origin vector, where each coordinate
is 0.

 `Vector3.new(x: float, y: float, z: float): Vector3`

The **new** constructor returns a vector composed by each given
component.

# Properties

----

## Magnitude

 `Vector3.Magnitude: float [readonly]`

The **Magnitude** field returns the length of the vector.

## Unit

 `Vector3.Unit: Vector3 [readonly]`

The **Unit** field returns a vector with the same direction, but a length
of 1.

## X

 `Vector3.X: float [readonly]`

The **X** field returns the X coordinate of the vector.

## Y

 `Vector3.Y: float [readonly]`

The **Y** field returns the Y coordinate of the vector.

## Z

 `Vector3.Z: float [readonly]`

The **Z** field returns the Z coordinate of the vector.

# Methods

----

## Cross

 `Vector3:Cross(op: Vector3): Vector3`

The **Cross** method returns the cross product of the vector and
*op*.

## Dot

 `Vector3:Dot(op: Vector3): float`

The **Dot** method returns the dot product of the vector and
*op*.

## FuzzyEq

 `Vector3:FuzzyEq(op: Vector3, epsilon: float): bool`

The **FuzzyEq** method returns whether the distance between the vector and
*op* is less than or equal to *epsilon*.

## Lerp

 `Vector3:Lerp(goal: Vector3, alpha: float): Vector3`

The **Lerp** method returns a vector linearly interpolated from the vector
to *goal* according to *alpha*, which has an interval of \[0, 1\].

# Operators

----

## \_\_add

 `Vector3 + Vector3 -> Vector3`

The **add** operator returns a vector where each corresponding component
of the two operands are summed.

## \_\_div

 `Vector3 / Vector3 -> Vector3`

The **div** operator returns a vector where each corresponding component
of the two operands are divided.

 `Vector3 / Number -> Vector3`

The **div** operator returns a vector where each component of the first
operand is divided by the second operand.

## \_\_eq

 `Vector3 == Vector3`

The **equal** operator returns true if both operands are Vector3, and each
corresponding component is equal.

## \_\_mul

 `Vector3 * Vector3 -> Vector3`

The **mul** operator returns a vector where each corresponding component
of the two operands are multiplied.

 `Vector3 * Number -> Vector3`

The **mul** operator returns a vector where each component of the first
operand is multiplied by the second operand.

## \_\_sub

 `Vector3 - Vector3 -> Vector3`

The **sub** operator returns a vector where each corresponding component
of the two operands are subtracted.

## \_\_unm

 `-Vector3 -> Vector3`

The **unm** operator returns a vector where each component is negated.