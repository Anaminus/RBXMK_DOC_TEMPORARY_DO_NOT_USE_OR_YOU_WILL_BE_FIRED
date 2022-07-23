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

This format has the same options as the [rbxl](/api/formats/rbxl)
format.