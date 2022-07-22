+++
weight = 1
title = "NumberSequenceKeypoint"
description = "A keypoint of a NumberSequence."
categories = ["API", "Type"]
+++

The **NumberSequenceKeypoint** type represents a single keypoint of a
NumberSequence.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a new keypoint. Creates a new keypoint with an envelope. |
| [Envelope](#envelope) | Property | The amount of variance allowed from the Value. |
| [Time](#time) | Property | The time location along the sequence. |
| [Value](#value) | Property | The base value. |
| [\_\_eq](#__eq) | Operator | Returns whether two NumberSequenceKeypoint values are equal. |

</div>

# Constructors

----

## new

 `NumberSequenceKeypoint.new(time: float, value: float): NumberSequenceKeypoint`

The **new** constructor returns a new NumberSequenceKeypoint, *time*
sets the Time field, and *value* sets the Value field.

 `NumberSequenceKeypoint.new(time: float, value: float, envelope: float): NumberSequenceKeypoint`

The **new** constructor returns a new NumberSequenceKeypoint, *time*
sets the Time field, *value* sets the Value field, and *envelope* sets
the Envelope field.

# Properties

----

## Envelope

 `NumberSequenceKeypoint.Envelope: float [readonly]`

The **Envelope** field returns the amount of variance allowed from the
value.

## Time

 `NumberSequenceKeypoint.Time: float [readonly]`

The **Time** field returns the temporal location of the keypoint in the
sequence. Has an interval of \[0, 1\].

## Value

 `NumberSequenceKeypoint.Value: float [readonly]`

The **Value** field returns the base value of the keypoint.

# Operators

----

## \_\_eq

 `NumberSequenceKeypoint == NumberSequenceKeypoint`

The **equal** operator returns true if both operands are
NumberSequenceKeypoint, and each corresponding component is equal.