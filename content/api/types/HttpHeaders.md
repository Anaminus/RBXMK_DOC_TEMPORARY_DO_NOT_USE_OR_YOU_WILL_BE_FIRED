+++
weight = 1
title = "HttpHeaders"
description = "Specifies headers of an HTTP request or response."
categories = ["API", "Type"]
+++

`type HttpHeaders = {[string]: string|{string}}`

The **HttpHeaders** type is a table that specifies the headers of an HTTP
request or response. Each entry consists of a header name mapped to a string
value. If a header requires multiple values, the name may be mapped to an array
of values instead.

For response headers, a header is always mapped to an array, and each array
will have at least one value.