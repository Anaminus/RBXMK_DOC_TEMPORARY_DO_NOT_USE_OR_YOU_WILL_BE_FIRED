+++
weight = 1
title = "patch.json"
description = "Encodes JSON patch data."
categories = ["API", "Format"]
+++

The **patch.json** format is defined for encoding JSON patches as defined
by [RFC 6902](https://datatracker.ietf.org/doc/html/rfc6902/).

| Direction | Type | Description |
| --- | --- | --- |
| Decode | JsonPatch | List of JsonOperation values. |
| Encode | JsonPatch | List of JsonOperation values. |

This format has the following options:

| Field | Type | Default | Description |
| --- | --- | --- | --- |
| Indent | string | `"\t"` | Determines the indentation of encoded content. If an empty string, then the content is minified. |