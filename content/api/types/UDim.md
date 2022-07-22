+++
weight = 1
title = "UDim"
description = "A dimension with a dynamic and constant component."
categories = ["API", "Type"]
+++

The **UDim** type represents one dimension with a dynamic and constant
component.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns a new UDim. |
| [Offset](#offset) | Property | The constant component. |
| [Scale](#scale) | Property | The dynamic component. |
| [\_\_add](#__add) | Operator | The sum of two UDim values. |
| [\_\_eq](#__eq) | Operator | Returns whether two UDim values are equal. |
| [\_\_sub](#__sub) | Operator | The difference between two UDim values. |
| [\_\_unm](#__unm) | Operator | The negation of the UDim. |

</div>

# Constructors

----

## new

 `UDim.new(scale: float, offset: int): UDim`

The **new** constructor returns a new UDim. *scale* sets the Scale
component, and *offset* sets the Offset component.

# Properties

----

## Offset

 `UDim.Offset: int [readonly]`

The **Offset** field returns the constant component of the UDim.

## Scale

 `UDim.Scale: float [readonly]`

The **Scale** field returns the dynamic component of the UDim.

# Operators

----

## \_\_add

 `UDim + UDim = UDim`

The **add** operator returns a UDim where each corresponding component of
the two operands are summed.

## \_\_eq

 `UDim == UDim`

The **equal** operator returns true if both operands are UDim, and each
corresponding component is equal.

## \_\_sub

 `UDim - UDim = UDim`

The **sub** operator returns a UDim where each corresponding component of
the two operands are subtracted.

## \_\_unm

 `-UDim = UDim`

The **unm** operator returns a UDim where each component is negated.