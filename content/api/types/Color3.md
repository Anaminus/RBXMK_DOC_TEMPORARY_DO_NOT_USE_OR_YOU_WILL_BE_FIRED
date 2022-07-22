+++
weight = 1
title = "Color3"
description = "A color in RGB space."
categories = ["API", "Type"]
+++

The **Color3** type represents a color in RGB space.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [fromHSV](#fromhsv) | Constructor | Returns a Color3 from hue, saturation, and value. |
| [fromRGB](#fromrgb) | Constructor | Returns a Color3 from 8-bit components. |
| [new](#new) | Constructor | Returns the zero Color3. Returns a Color3 from components. |
| [B](#b) | Property | The blue component. |
| [G](#g) | Property | The green component. |
| [R](#r) | Property | The red component. |
| [Lerp](#lerp) | Method | Linearly interpolates between two colors. |
| [ToHSV](#tohsv) | Method | Converts to hue, saturation, and value. |
| [\_\_eq](#__eq) | Operator | Returns whether two Color3 values are equal. |

</div>

# Constructors

----

## fromHSV

 `Color3.fromHSV(h: float, s: float, v: float): Color3`

The **fromHSV** constructor returns a Color3 from the given hue,
saturation, and value.

## fromRGB

 `Color3.fromRGB(r: int, g: int, b: int): Color3`

The **fromRGB** constructor returns a Color3 from the given red, green,
and blue components, each having an interval of \[0, 255\].

## new

 `Color3.new(): Color3`

The **new** constructor returns the zero value for Color3, with each
component being zero, resulting in the color black.

 `Color3.new(r: float, g: float, b: float): Color3`

The **new** constructor returns a Color3 from the given red, green, and
blue components, each having an interval of \[0, 1\].

# Properties

----

## B

 `Color3.B: float [readonly]`

The **B** field returns the blue component of the color.

## G

 `Color3.G: float [readonly]`

The **G** field returns the green component of the color.

## R

 `Color3.R: float [readonly]`

The **R** field returns the red component of the color.

# Methods

----

## Lerp

 `Color3:Lerp(goal: Color3, alpha: float): Color3`

The **Lerp** method returns a Color3 linearly interpolated from the color
to *goal* according to *alpha*, which has an interval of \[0, 1\].

## ToHSV

 `Color3:ToHSV(): (h: float, s: float, v: float)`

The **ToHSV** method returns the hue, saturation, and value approximated
from the color.

# Operators

----

## \_\_eq

 `Color3 == Color3`

The **equal** operator returns true if both operands are Color3, and each
corresponding component is equal.