+++
weight = 1
title = "HttpOptions"
description = "Specifies how an HTTP request is made."
categories = ["API", "Type"]
+++

`type HttpOptions = {Body: any?, Cookies: Cookies?, Headers: HttpHeaders?, Method: string?, RequestFormat: FormatSelector?, ResponseFormat: FormatSelector?, URL: string}`

The **HttpOptions** type is a table that specifies how an HTTP request is
made. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| URL | [string](/api/types/string) | The URL to make to request to. |
| Method | [string](/api/types/string)? | The HTTP method. Defaults to GET. |
| RequestFormat | [FormatSelector](/api/types/FormatSelector)? | The format used to encode the request body. |
| ResponseFormat | [FormatSelector](/api/types/FormatSelector)? | The format used to decode the response body. |
| Headers | [HttpHeaders](/api/types/HttpHeaders)? | The HTTP headers to include with the request. |
| Cookies | [Cookies](/api/types/Cookies)? | Cookies to append to the Cookie header. |
| Body | [any](/api/types/string)? | The body of the request, to be encoded by the specified format. |

If RequestFormat is unspecified, then no request body is sent. If
ResponseFormat is unspecified, then no response body is returned.

Use of the Cookies field ensures that cookies sent with the request are
well-formed, and is preferred over setting the Cookie header directly.