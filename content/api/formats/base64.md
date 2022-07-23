+++
weight = 1
title = "base64"
description = "Encodes data in Base64."
categories = ["API", "Format"]
+++

The **base64** format is defined for encoding strings in the [Base64](https://en.wikipedia.org/wiki/Base64) format.

| Direction | Type | Description |
| --- | --- | --- |
| Decode | BinaryString | Raw binary data. |
| Encode | Stringable | Any string-like value. |

This format has the following options:

| Field | Type | Default | Description |
| --- | --- | --- | --- |
| Width | string | `0` | Causes the encoded result to be wrapped to the given number of characters. Does not wrap if the width is less than 1. |