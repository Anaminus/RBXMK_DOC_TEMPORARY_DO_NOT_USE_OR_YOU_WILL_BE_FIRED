+++
weight = 1
title = "bin"
description = "Encodes raw bytes."
categories = ["API", "Format"]
+++

The **bin** format encodes string-like values with the assurance that the
bytes will be interpreted exactly as-is.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | BinaryString | Raw binary data. |
| Encode | Stringable | Any string-like value. |

This format has no options.