+++
weight = 110
title = "math"
+++

The **math** library is an extension to the standard library that includes
the same additions to [Roblox's\
math library](https://developer.roblox.com/en-us/api-reference/lua-docs/math):

| Item | Kind | Description |
| --- | --- | --- |
| [clamp](#clamp) | Function | Returns a number clamped between a minimum and maximum. |
| [log](#log) | Function | Includes optional base argument. |
| [round](#round) | Function | Rounds a number to the nearest integer. |
| [sign](#sign) | Function | Returns the sign of a number. |

# Functions

----

## clamp

 `math.clamp(x: number, min: number, max: number): number`

The **clamp** function returns *x* clamped so that it is not less
than *min* or greater than *max*.

## log

 `math.log(x: number, base: number? = 𝑒): number`

The **log** function returns the logarithm of *x* in *base*. The
default for *base* is `e`, returning the natural logarithm of
*x*.

## round

 `math.round(x: number): number`

The **round** function returns *x* rounded to the nearest integer.
The function rounds half away from zero.

## sign

 `math.sign(x: number): number`

The **sign** function returns the sign of *x*: `1` if
*x* is greater than zero, `-1` of *x* is less than zero,
and `0` if *x* equals zero.