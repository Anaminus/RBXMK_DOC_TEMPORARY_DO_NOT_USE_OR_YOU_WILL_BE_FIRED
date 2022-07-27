+++
weight = 1
title = "modulescript.luau"
description = "Encodes ModulesScripts."
categories = ["API", "Format"]
+++

The **modulescript.luau** format is a shortcut for decoding Luau code into
a ModuleScript instance, where the content is assigned to the Source
property.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | [Instance](/api/types/Instance) | A ModuleScript with a Source property. |
| Encode | Stringable | Any string-like value. |