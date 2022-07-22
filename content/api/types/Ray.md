+++
weight = 1
title = "Ray"
description = "A line extending infinitely in one direction."
categories = ["API", "Type"]
+++

The **Ray** type represents a line that extends infinitely in one
direction.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a new Ray. |
| [Direction](#direction) | Property | The direction of the ray. |
| [Origin](#origin) | Property | The position of the ray. |
| [ClosestPoint](#closestpoint) | Method | Returns the nearest point on the ray. |
| [Distance](#distance) | Method | Returns distance to the nearest point on the ray. |
| [\_\_eq](#__eq) | Operator | Returns whether two Ray values are equal. |

</div>

# Constructors

----

## new

 `Ray.new(origin: Vector3, direction: Vector3): Ray`

The **new** constructor returns a Ray, where *origin* sets the
Origin, and *direction* sets the Direction.

# Properties

----

## Direction

 `Ray.Direction: Vector3 [readonly]`

The **Direction** field returns the direction of the ray.

## Origin

 `Ray.Origin: Vector3 [readonly]`

The **Origin** field returns the position of the ray.

# Methods

----

## ClosestPoint

 `Ray:ClosestPoint(point: Vector3): Vector3`

The **ClosestPoint** method returns the position on the ray that is
nearest to *point*.

## Distance

 `Ray:Distance(point: Vector3): float`

The **Distance** method returns the distance between *point* and the
point on the ray nearest to *point*.

# Operators

----

## \_\_eq

 `Ray == Ray`

The **equal** operator returns true if both operands are Ray, and each
corresponding component is equal.