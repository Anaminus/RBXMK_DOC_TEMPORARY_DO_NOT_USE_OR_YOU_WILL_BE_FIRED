+++
weight = 1
title = "Region3"
description = "An axis-aligned rectangular cuboid."
categories = ["API", "Type"]
+++

The **Region3** type represents an axis-aligned three-dimensional
rectangular cuboid with a lower and upper boundary.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns Region3 composed by two Vector3s. |
| [CFrame](#cframe) | Property | The center of the region. |
| [Size](#size) | Property | The size of the region. |
| [ExpandToGrid](#expandtogrid) | Method | Expands the region to align to a grid. |
| [\_\_eq](#__eq) | Operator | Returns whether two Region3 values are equal. |

</div>

# Constructors

----

## new

 `Region3.new(min: Vector3, max: Vector3): Region3`

The **new** constructor returns a Region3 composed by two Vector3 values,
where *min* is the lower bound of the region, and *max* is the upper
bound.

# Properties

----

## CFrame

 `Region3.CFrame: CFrame [readonly]`

The **CFrame** field returns a CFrame with its Position located at the
center of the region.

## Size

 `Region3.Size: Vector3 [readonly]`

The **Size** returns the size of the region.

# Methods

----

## ExpandToGrid

 `Region3:ExpandToGrid(resolution: float): Region3`

The **ExpandToGrid** method returns the region expanded so that is lower
and upper bounds align to *resolution*. If *resolution* is 0, the
region is returned unchanged.

# Operators

----

## \_\_eq

 `Region3 == Region3`

The **equal** operator returns true if both operands are Region3, and each
corresponding component is equal.