+++
weight = 1
title = "Font"
description = "The font used to render text."
categories = ["API", "Type"]
+++

The **Font** type represents the description of a font.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a new Font. |
| [CachedFaceId](#cachedfaceid) | Property | A sequential value. |
| [Family](#family) | Property | Path to a font family. |
| [Style](#style) | Property | Whether the text is italic. |
| [Weight](#weight) | Property | The weight of font text. |
| [\_\_eq](#__eq) | Operator | Returns whether two Font values are equal. |

</div>

# Constructors

----

## new

 `Font.new(family: Content, weight: int, style: int): Font`

The **new** constructor returns a Font composed of the components from
each argument.

# Properties

----

## CachedFaceId

 `Font.CachedFaceId: Content [readonly]`

The **CachedFaceId** property is an internal value representing a path to
resolved font data.

## Family

 `Font.Family: Content [readonly]`

The **Family** property points to a font file.

## Style

 `Font.Style: int [readonly]`

The **Style** property determines whether the text is italic. 0 means
normal, and 1 means italic.

## Weight

 `Font.Weight: int [readonly]`

The **Weight** property determines the thickness of the text. The value is
a standard [OpenType\
weight value](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#usweightclass), where 400 is regular, 700 is bold, 100 is thin, and 900 is
heavy.

# Operators

----

## \_\_eq

 `Font == Font`

The **equal** operator returns true if both operands are Font, and each
corresponding component is equal.