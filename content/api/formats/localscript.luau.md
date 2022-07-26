+++
weight = 1
title = "localscript.luau"
description = "Encodes LocalScripts."
categories = ["API", "Format"]
+++

The **localscript.luau** format is a shortcut for decoding Luau code into
a LocalScript instance, where the content is assigned to the Source
property.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | [Instance](/api/types/Instance) | A LocalScript with a Source property. |
| Encode | Stringable | Any string-like value. |

This format has no options.