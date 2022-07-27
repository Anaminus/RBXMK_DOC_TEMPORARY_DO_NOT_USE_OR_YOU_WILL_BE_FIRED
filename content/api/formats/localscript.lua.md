+++
weight = 1
title = "localscript.lua"
description = "Encodes LocalScripts."
categories = ["API", "Format"]
+++

The **localscript.lua** format is a shortcut for decoding Lua code into a
LocalScript instance, where the content is assigned to the Source property.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | [Instance](/api/types/Instance) | A LocalScript with a Source property. |
| Encode | Stringable | Any string-like value. |