+++
weight = 1
title = "Rect"
description = "An axis-aligned rectangle."
categories = ["API", "Type"]
+++

The **Rect** type represents an axis-aligned two-dimensional rectangle
with a lower and upper boundary.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns a Rect composed by two Vector2s. Returns a Rect composed by boundary components. *minX* and *minY* compose the lower bounds, and *maxX* and *maxY* compose the upper bounds. |
| [Height](#height) | Property | The height of the rectangle. |
| [Max](#max) | Property | The upper bounds of the rectangle. |
| [Min](#min) | Property | The lower bounds of the rectangle. |
| [Width](#width) | Property | The width of the rectangle. |
| [\_\_eq](#__eq) | Operator | Returns whether two Rect values are equal. |

</div>

# Constructors

----

## new

 `Rect.new(min: Vector2, max: Vector2): Rect`

The **new** constructor returns a Rect composed by two Vector2s.
*min* is the lower bounds, and *max* is the upper bounds.

 `Rect.new(minX: float, minY: float, maxX: float, maxY: float): Rect`

The **new** constructor returns a Rect composed by boundary
components.

# Properties

----

## Height

 `Rect.Height: float [readonly]`

The **Height** field returns the height of the rectangle, or the
difference between the upper and lower bounds on the Y axis.

## Max

 `Rect.Max: Vector2 [readonly]`

The **Max** field returns the upper bounds of the rectangle.

## Min

 `Rect.Min: Vector2 [readonly]`

The **Min** field returns the lower bounds of the rectangle.

## Width

 `Rect.Width: float [readonly]`

The **Width** field returns the width of the rectangle, or the difference
between the upper and lower bounds on the X axis.

# Operators

----

## \_\_eq

 `Rect == Rect`

The **equal** operator returns true if both operands are Rect, and each
corresponding component is equal.