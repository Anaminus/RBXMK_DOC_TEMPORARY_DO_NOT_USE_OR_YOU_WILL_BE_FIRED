+++
weight = 1
title = "AttrConfig"
description = "Configures instance attributes."
categories = ["API", "Type"]
+++

The **AttrConfig** type configures how an instance encodes and decodes
attributes.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Creates a new AttrConfig. |
| [Property](#property) | Property | The property that attributes are applied to. |

</div>

# Constructors

----

## new

 `AttrConfig.new(property: string): AttrConfig`

The **new** constructor creates a new AttrConfig. *property* sets the
[Property](/api/types/AttrConfig#property) field, defaulting to an empty
string.

# Properties

----

## Property

 `AttrConfig.Property: string`

The **Property** property determines which property of an [Instance](/api/types/Instance) attributes are applied to. If an empty string,
instances will default to "AttributesSerialize".