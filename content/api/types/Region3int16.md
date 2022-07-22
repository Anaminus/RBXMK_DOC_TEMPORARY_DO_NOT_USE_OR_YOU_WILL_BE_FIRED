+++
weight = 1
title = "Region3int16"
description = "An axis-aligned rectangular cuboid with 16-bit integer precision."
categories = ["API", "Type"]
+++

The **Region3** type represents an axis-aligned three-dimensional
rectangular cuboid with a lower and upper boundary, with each component having
16-bit integer precision.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns Region3 composed by two Vector3s. |
| [Max](#max) | Property | The upper bounds of the region. |
| [Min](#min) | Property | The lower bounds of the region. |
| [\_\_eq](#__eq) | Operator | Returns whether two Region3int16 values are equal. |

</div>

# Constructors

----

## new

 `Region3int16.new(min: Vector3int16, max: Vector3int16): Region3int16`

The **new** constructor returns a Region3 composed by two Vector3int16
values, where *min* is the lower bound of the region, and *max* is the
upper bound.

# Properties

----

## Max

 `Region3int16.Max: Vector3int16 [readonly]`

The **Max** field returns the upper bounds of the region.

## Min

 `Region3int16.Min: Vector3int16 [readonly]`

The **Min** field returns the lower bounds of the region.

# Operators

----

## \_\_eq

 `Region3int16 == Region3int16`

The **equal** operator returns true if both operands are Region3int16, and
each corresponding component is equal.