+++
weight = 100
title = "math"
description = "Common mathematical functions."
categories = ["API", "Struct"]
+++

The **math** library contains common mathematical functions and
variables.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [huge](#huge) | Field | The value >= any other numerical value. |
| [pi](#pi) | Field | The value of π. |
| [abs](#abs) | Function | Returns the absolute value of *x*. |
| [acos](#acos) | Function | Returns the arc cosine of *x*. |
| [asin](#asin) | Function | Returns the arc sine of *x*. |
| [atan](#atan) | Function | Returns the arc tangent of *x*. |
| [atan2](#atan2) | Function | Returns the arc tangent of *y*/ *x*. |
| [ceil](#ceil) | Function | Returns the smallest integer >= *x*. |
| [cos](#cos) | Function | Returns the cosine of *x*. |
| [cosh](#cosh) | Function | Returns the hyperbolic cosine of *x*. |
| [deg](#deg) | Function | Returns angle *x* in degrees. |
| [exp](#exp) | Function | Returns e^ *x*. |
| [floor](#floor) | Function | Returns the largest integer <= *x*. |
| [fmod](#fmod) | Function | Returns the remainder of *x*/ *y*, rounding towards 0. |
| [frexp](#frexp) | Function | Returns such that `x = m2^e`. |
| [ldexp](#ldexp) | Function | Returns `m2^e`. |
| [max](#max) | Function | Returns the maximum value. |
| [min](#min) | Function | Returns the minimum value. |
| [modf](#modf) | Function | Returns the integral and fractional part of *x*. |
| [pow](#pow) | Function | Returns `x^y`. |
| [rad](#rad) | Function | Returns angle *x* in radians. |
| [random](#random) | Function | Returns a random number in the range \[0, 1). Returns a random number in the range \[1, *m*\]. Returns a random number in the range \[ *m*, *n*\]. |
| [randomseed](#randomseed) | Function | Sets *x* as the seed for the random number generator. |
| [sin](#sin) | Function | Returns the sine of *x*. |
| [sinh](#sinh) | Function | Returns the hyperbolic sine of *x*. |
| [sqrt](#sqrt) | Function | Returns the square root of *x*. |
| [tan](#tan) | Function | Returns the tangent of *x*. |
| [tanh](#tanh) | Function | Returns the hyperbolic tangent of *x*. |

</div>

# Fields

----

## huge

 `math.huge: number [readonly]`

The **huge** value is greater than or equal to any other numerical value
(infinity).

## pi

 `math.pi: number [readonly]`

The **pi** value is the value of the mathematical constant pi.

# Functions

----

## abs

 `math.abs(x: number): number`

The **abs** function returns the absolute value of *x*.

## acos

 `math.acos(x: number): number`

The **acos** function returns the arc cosine of *x*, in radians.

## asin

 `math.asin(x: number): number`

The **asin** function returns the arc sine of *x*, in radians.

## atan

 `math.atan(x: number): number`

The **atan** function returns the arc tangent of *x*, in radians.

## atan2

 `math.atan2(x: number, y: number): number`

The *atan2* function returns the arc tangent of *y* divided by
*x*, in radians. The signs of both arguments are used to find the quadrant
of the result. The case of *x* being 0 is also handled.

## ceil

 `math.ceil(x: number): integer`

The **ceil** function returns the smallest integer less than or equal to
*x*.

## cos

 `math.cos(x: number): number`

The **cos** function returns the cosine of *x*, which is assumed to
be in radians.

## cosh

 `math.cosh(x: number): number`

The **cosh** function returns the hyperbolic cosine of *x*.

## deg

 `math.deg(x: number): number`

The **deg** function returns angle *x* (radians) in degrees.

## exp

 `math.exp(x: number): number`

The **exp** function returns e^ *x*, where e is Euler's number.

## floor

 `math.floor(x: number): integer`

The **floor** function returns the largest integer less than or equal to
*x*.

## fmod

 `math.fmod(x: number, y: number): number`

The **fmod** function returns the remainder of *x* divided by
*y* with the quotient rounded towards 0.

## frexp

 `math.frexp(x: number): (m: number, e: integer)`

The **frexp** function returns *m* and *e* such that `x =
m2^e`. *m* will be in the range \[0.5, 1), or 0 when *x* is
0.

## ldexp

 `math.ldexp(m: number, e: integer): number`

The **ldexp** function returns `m2^e`.

## max

 `math.max(...: number): number`

The **max** function returns the largest value among the given
arguments.

## min

 `math.min(...: number): number`

The **min** function returns the smallest value among the given
arguments.

## modf

 `math.modf(x: number): (integer, number)`

The **modf** function returns the integral and fractional part of
*x*.

## pow

 `math.pow(x: number): number`

The **pow** function returns `x^y`.

## rad

 `math.rad(x: number): number`

The **rad** function returns angle *x* (degrees) in radians.

## random

 `math.random(): number`

The **random** function returns a uniform pseudo-random real number in the
range \[0, 1).

 `math.random(m: integer): number`

The **random** function returns a uniform pseudo-random integer in the
range \[1, *m*\].

 `math.random(m: integer, n: integer): number`

The **random** function returns a uniform pseudo-random integer in the
range \[ *m*, *n*\].

## randomseed

 `math.randomseed(x: number)`

The **randomseed** function sets *x* as the seed for the random
number generator.

## sin

 `math.sin(x: number): number`

The **sin** function returns the sine of *x*, which is assumed to be
in radians.

## sinh

 `math.sinh(x: number): number`

The **sinh** function returns the hyperbolic sine of *x*.

## sqrt

 `math.sqrt(x: number): number`

The **sqrt** function returns the square root of *x*.

## tan

 `math.tan(x: number): number`

The **tan** function returns the tangent of *x*, which is assumed to
be in radians.

## tanh

 `math.tanh(x: number): number`

The **tanh** function returns the hyperbolic tangent of *x*.