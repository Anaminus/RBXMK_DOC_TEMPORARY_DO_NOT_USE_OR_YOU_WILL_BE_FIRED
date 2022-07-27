+++
weight = 1
title = "script.luau"
description = "Encodes Scripts."
categories = ["API", "Format"]
+++

The **script.luau** format is a shortcut for decoding Luau code into a
Script instance, where the content is assigned to the Source property.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | [Instance](/api/types/Instance) | A Script with a Source property. |
| Encode | Stringable | Any string-like value. |