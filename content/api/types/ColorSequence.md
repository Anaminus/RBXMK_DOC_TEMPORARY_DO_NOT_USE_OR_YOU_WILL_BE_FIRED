+++
weight = 1
title = "ColorSequence"
description = "An interpolated sequence of colors."
categories = ["API", "Type"]
+++

The **ColorSequence** type represents an interpolated sequence of
colors.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | The **new** constructor returns a ColorSequence with a single color. Returns a sequence with two colors. Returns a sequence composed of the given keypoints. |
| [Keypoints](#keypoints) | Property | The keypoints of the sequence. |
| [\_\_eq](#__eq) | Operator | Returns whether two ColorSequence values are equal. |

</div>

# Constructors

----

## new

 `ColorSequence.new(color: Color3): ColorSequence`

no content for topic "Types/ColorSequence:Constructors/new/Single/Description"
`ColorSequence.new(color0: Color3, color1: Color3): ColorSequence`

The **new** constructor returns a ColorSequence that interpolates between
*color0* and *color1*.

 `ColorSequence.new(keypoints: {ColorSequenceKeypoint}): ColorSequence`

The **new** constructor returns a ColorSequence composed from
*keypoints*. Each keypoint must be ordered ascending by their Time field.
The first keypoint must have a Time of 0, and the last keypoint must have a Time
of 1.

# Properties

----

## Keypoints

 `ColorSequence.Keypoints: {ColorSequenceKeypoint} [readonly]`

The **Keypoints** field returns the ColorSequenceKeypoints of the
sequence.

# Operators

----

## \_\_eq

 `ColorSequence == ColorSequence`

The **equal** operator returns true if both operands are ColorSequence,
and each corresponding keypoint is equivalent.