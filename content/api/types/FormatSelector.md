+++
weight = 1
title = "FormatSelector"
description = "Selects a format with an optional configuration."
categories = ["API", "Type"]
+++

`type FormatSelector = string|{[string]: any, Format: string}`

The **FormatSelector** type selects a [format](/api/formats),
and optionally configures the format.

If a table, then the Format field indicates the name of the format to use,
and remaining fields are options that configure the format, which depend on the
format specified. All such fields are optional.

If a string, it is the name of the format to use, and specifies no
options.