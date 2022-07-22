+++
weight = 1
title = "ColorSequenceKeypoint"
description = "A keypoint of a ColorSequence."
categories = ["API", "Type"]
+++

The **ColorSequenceKeypoint** type represents a single keypoint of a
ColorSequence.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a new keypoint. Creates a new keypoint with an envelope. |
| [Envelope](#envelope) | Property | The amount of variance allowed from the Value. |
| [Time](#time) | Property | The time location along the sequence. |
| [Value](#value) | Property | The base value. |
| [\_\_eq](#__eq) | Operator | Returns whether two ColorSequenceKeypoint values are equal. |

</div>

# Constructors

----

## new

 `ColorSequenceKeypoint.new(time: float, color: Color3): ColorSequenceKeypoint`

The **new** constructor returns a new ColorSequenceKeypoint, *time*
sets the Time field, and *color* sets the Value field.

 `ColorSequenceKeypoint.new(time: float, color: Color3, envelope: float): ColorSequenceKeypoint`

The **new** constructor returns a new ColorSequenceKeypoint, *time*
sets the Time field, *color* sets the Value field, and *envelope* sets
the Envelope field.

# Properties

----

## Envelope

 `ColorSequenceKeypoint.Envelope: float [readonly]`

The **Envelope** field returns the amount of variance allowed from the
value.

## Time

 `ColorSequenceKeypoint.Time: float [readonly]`

The **Time** field returns the temporal location of the keypoint in the
sequence. Has an interval of \[0, 1\].

## Value

 `ColorSequenceKeypoint.Value: Color3 [readonly]`

The **Value** field returns the base value of the keypoint.

# Operators

----

## \_\_eq

 `ColorSequenceKeypoint == ColorSequenceKeypoint`

The **equal** operator returns true if both operands are
ColorSequenceKeypoint, and each corresponding component is equal.