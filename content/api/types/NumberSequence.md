+++
weight = 1
title = "NumberSequence"
description = "An interpolated sequence of numbers."
categories = ["API", "Type"]
+++

The **NumberSequence** type represents an interpolated sequence of
numbers.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | The **new** constructor returns a NumberSequence with a single number. Returns a sequence with two numbers. Returns a sequence composed of the given keypoints. |
| [Keypoints](#keypoints) | Property | The keypoints of the sequence. |
| [\_\_eq](#__eq) | Operator | Returns whether two NumberSequence values are equal. |

</div>

# Constructors

----

## new

 `NumberSequence.new(value: float): NumberSequence`

no content for topic "Types/NumberSequence:Constructors/new/Single/Description"
`NumberSequence.new(value0: float, value1: float): NumberSequence`

The **new** constructor returns a NumberSequence that interpolates between
*value0* and *value1*.

 `NumberSequence.new(keypoints: {NumberSequenceKeypoint}): NumberSequence`

The **new** constructor returns a NumberSequence composed from
*keypoints*. Each keypoint must be ordered ascending by their Time field.
The first keypoint must have a Time of 0, and the last keypoint must have a Time
of 1.

# Properties

----

## Keypoints

 `NumberSequence.Keypoints: {NumberSequenceKeypoint} [readonly]`

The **Keypoints** field returns the NumberSequenceKeypoints of the
sequence.

# Operators

----

## \_\_eq

 `NumberSequence == NumberSequence`

The **equal** operator returns true if both operands are NumberSequence,
and each corresponding keypoint is equivalent.