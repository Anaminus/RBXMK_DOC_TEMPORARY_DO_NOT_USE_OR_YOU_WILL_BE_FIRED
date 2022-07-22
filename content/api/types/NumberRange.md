+++
weight = 1
title = "NumberRange"
description = "A range of numbers."
categories = ["API", "Type"]
+++

The **NumberRange** type represents a range of numbers between a minimum
and maximum.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns a range with a single value. Returns a range with between two values. |
| [Max](#max) | Property | The maximum value. |
| [Min](#min) | Property | The minimum value. |
| [\_\_eq](#__eq) | Operator | Returns whether two NumberRange values are equal. |

</div>

# Constructors

----

## new

 `NumberRange.new(value: float): NumberRange`

The **new** constructor returns a NumberRange where *value* is both
the minimum and maximum.

 `NumberRange.new(minimum: float, maxmimum: float): NumberRange`

The **new** constructor returns a NumberRange where *minimum* is the
minimum value and *maximum* is the maximum value. Throws an error if
*minimum* is greater than *maximum*.

# Properties

----

## Max

 `NumberRange.Max: float [readonly]`

The **Max** field returns the maximum possible value in the range.

## Min

 `NumberRange.Min: float [readonly]`

The **Min** field returns the minimum possible value in the range.

# Operators

----

## \_\_eq

 `NumberRange == NumberRange`

The **equal** operator returns true if both operands are NumberRange, and
each corresponding component is equal.