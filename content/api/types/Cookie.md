+++
weight = 1
title = "Cookie"
description = "An HTTP cookie."
categories = ["API", "Type"]
+++

The **Cookie** type contains information about an HTTP cookie.

For security reasons, the value of the cookie cannot be accessed.

Cookie is immutable. A Cookie can be created with the [Cookie.new](/api/types/Cookie#new) constructor. Additionally, Cookies can be
fetched from known locations with the [Cookie.from](/api/types/Cookie#from)
function.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [from](#from) | Constructor | Gets cookies from a known location. |
| [new](#new) | Constructor | Creates a new cookie. |
| [Name](#name) | Property | The name of the cookie. |
| [\_\_eq](#__eq) | Operator | Returns whether two Cookie values are equal. |

</div>

# Constructors

----

## from

 `Cookie.from(location: string ["studio"]): (cookies: Cookies)`

The **from** constructor retrieves cookies from a known location.
*location* is case-insensitive.

The following locations are implemented:

| Location | Description |
| --- | --- |
| `studio` | Returns the cookies used for authentication when logging into Roblox Studio. |

Returns nil if no cookies could be retrieved from the location. Throws an
error if an unknown location is given.

## new

 `Cookie.new(name: string, value: string): Cookie`

The **new** constructor creates a new cookie object.

# Properties

----

## Name

 `Cookie.Name: string [readonly]`

The **Name** field is the name of the cookie.

# Operators

----

## \_\_eq

 `Cookie == Cookie`

The **equal** operator returns true if both operands are Cookie values,
and their Name properties are equal, and their internal values are equal.