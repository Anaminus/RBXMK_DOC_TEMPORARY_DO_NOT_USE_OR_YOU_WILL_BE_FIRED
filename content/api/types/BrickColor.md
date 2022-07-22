+++
weight = 1
title = "BrickColor"
description = "A color from a predefined collection."
categories = ["API", "Type"]
+++

The **BrickColor** type represents a color from a predefined
collection.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [Black](#black) | Constructor | Returns a black color. |
| [Blue](#blue) | Constructor | Returns a blue color. |
| [DarkGray](#darkgray) | Constructor | Returns a dark gray color. |
| [Gray](#gray) | Constructor | Returns a gray color. |
| [Green](#green) | Constructor | Returns a green color. |
| [Red](#red) | Constructor | Returns a red color. |
| [White](#white) | Constructor | Returns a white color. |
| [Yellow](#yellow) | Constructor | Returns a yellow color. |
| [new](#new) | Constructor | Creates a BrickColor from a numeric value. Creates a BrickColor from color components. Creates a BrickColor from a name. Creates a BrickColor from a Color3. |
| [palette](#palette) | Constructor | Returns a BrickColor from a predefined list of colors. |
| [random](#random) | Constructor | Returns a random BrickColor. |
| [B](#b) | Property | The blue component. |
| [Color](#color) | Property | The Color3 corresponding to the BrickColor. |
| [G](#g) | Property | The green component. |
| [Name](#name) | Property | The name of the BrickColor. |
| [Number](#number) | Property | The numeric value of the BrickColor. |
| [R](#r) | Property | The red component. |
| [\_\_eq](#__eq) | Operator | Returns whether two BrickColor values are equal. |

</div>

# Constructors

----

## Black

 `BrickColor.Black(): BrickColor`

The **Black** constructor returns the "Black" brick color.

## Blue

 `BrickColor.Blue(): BrickColor`

The **Blue** constructor returns the "Bright blue" brick color.

## DarkGray

 `BrickColor.DarkGray(): BrickColor`

The **DarkGray** constructor returns the "Dark stone grey" brick
color.

## Gray

 `BrickColor.Gray(): BrickColor`

The **Gray** constructor returns the "Medium stone grey" brick color.

## Green

 `BrickColor.Green(): BrickColor`

The **Green** constructor returns the "Dark green" brick color.

## Red

 `BrickColor.Red(): BrickColor`

The **Red** constructor returns the "Bright red" brick color.

## White

 `BrickColor.White(): BrickColor`

The **White** constructor returns the "White" brick color.

## Yellow

 `BrickColor.Yellow(): BrickColor`

The **Yellow** constructor returns the "Bright yellow" brick color.

## new

 `BrickColor.new(value: int): BrickColor`

The **new** constructor returns the BrickColor for which the Number field
is equal to *value*.

 `BrickColor.new(r: float, g: float, b: float): BrickColor`

The **new** constructor returns the BrickColor that is nearest to the
given color components.

 `BrickColor.new(name: string): BrickColor`

The **new** constructor returns the BrickColor for which the Name field is
equal to *name*.

 `BrickColor.new(color: Color3): BrickColor`

The **new** constructor returns the BrickColor that is nearest to
*color*.

## palette

 `BrickColor.palette(index: int): BrickColor`

The **palette** constructors returns the BrickColor corresponding to
*index* in a predefined list of 128 colors. An error is thrown if
*index* is not between 0 and 127.

## random

 `BrickColor.random(): BrickColor`

The **random** constructor returns a randomly selected BrickColor.

# Properties

----

## B

 `BrickColor.B: float [readonly]`

The **B** field is the blue component of the BrickColor.

## Color

 `BrickColor.Color: Color3 [readonly]`

The **Color** field is the Color3 value corresponding to the
BrickColor.

## G

 `BrickColor.G: float [readonly]`

The **G** field is the green component of the BrickColor.

## Name

 `BrickColor.Name: string [readonly]`

The **Name** field is a name that describes the BrickColor.

## Number

 `BrickColor.Number: int [readonly]`

The **Number** field is a numeric value that uniquely identifies the
BrickColor.

## R

 `BrickColor.R: float [readonly]`

The **R** field is the red component of the BrickColor.

# Operators

----

## \_\_eq

 `BrickColor == BrickColor`

The **equal** operator returns true if both operands are BrickColor, and
their Number fields are equal.