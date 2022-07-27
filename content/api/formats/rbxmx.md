+++
weight = 1
title = "rbxmx"
description = "Encodes XML model data."
categories = ["API", "Format"]
+++

The **rbxmx** format encodes Instances in the Roblox XML model format.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | [DataModel](/api/types/DataModel) | A DataModel instance. |
| Encode | [DataModel](/api/types/DataModel) | A DataModel instance. |
| Encode | [Instance](/api/types/Instance) | A single instance, interpreted as a child to a DataModel. |
| Encode | Objects | A list of Instances, interpreted as children to a DataModel. |

# Options

----

## Desc

**Type:** `Desc | bool | nil`

**Default:** `nil`

Sets the descriptor to be used when encoding or decoding. If
`false`, then no descriptor is used. Otherwise, the descriptor of the
root instance is used **with all descendants**, falling back to [globalDesc](/api/libraries/rbxmk#globaldesc).

## DescMode

**Type:** `string`

**Default:** `"NonStrict"`

Determines how deviations from the descriptor are handled.
`"NonStrict"` causes deviations to be ignored. `"Strict"`
causes an error to be thrown for the first deviation. `"Preserve"`
tries to retain as much information as possible, usually by behaving as if no
descriptor is set.