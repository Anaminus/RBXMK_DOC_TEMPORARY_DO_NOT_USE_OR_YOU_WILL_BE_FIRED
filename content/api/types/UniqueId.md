+++
weight = 1
title = "UniqueId"
description = "A unique identifier."
categories = ["API", "Type"]
+++

The **UniqueId** type represents the value of a unique identifier.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Generates a new UniqueId. Returns a UniqueId from components. |
| [Index](#index) | Property | A sequential value. |
| [Random](#random) | Property | A random value. |
| [Time](#time) | Property | A time-based value. |
| [\_\_eq](#__eq) | Operator | Returns whether two UniqueId values are equal. |

</div>

# Constructors

----

## new

 `UniqueId.new(): UniqueId`

The **new** constructor returns a new UniqueId generated from an internal
source. The method to generate the value is similar to Roblox's
implementation.

 `UniqueId.new(random: int64, time: int64, index: int64): UniqueId`

The **new** constructor returns a UniqueId composed of the components from
each argument.

# Properties

----

## Index

 `UniqueId.Index: int64 [readonly]`

The **Index** property represents the sequential portion of the unique
identifier. This value is generated such that it is almost certain to be unique,
but is also predictable.

## Random

 `UniqueId.Random: int64 [readonly]`

The **Random** property represents the random portion of the unique
identifier. This value is generated from a pseudo-random source.

## Time

 `UniqueId.Time: int64 [readonly]`

The **Time** property represents the time portion of the unique identifier.
This value generated based on the time.

# Operators

----

## \_\_eq

 `UniqueId == UniqueId`

The **equal** operator returns true if both operands are UniqueId, and
each corresponding component is equal.