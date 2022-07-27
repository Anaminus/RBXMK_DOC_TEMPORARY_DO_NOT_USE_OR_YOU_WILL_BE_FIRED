+++
weight = 1
title = "script.lua"
description = "Encodes Scripts."
categories = ["API", "Format"]
+++

The **script.lua** format is a shortcut for decoding Lua code into a
Script instance, where the content is assigned to the Source property.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | [Instance](/api/types/Instance) | A Script with a Source property. |
| Encode | Stringable | Any string-like value. |