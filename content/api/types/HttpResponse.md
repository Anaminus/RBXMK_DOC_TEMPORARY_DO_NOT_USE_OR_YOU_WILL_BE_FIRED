+++
weight = 1
title = "HttpResponse"
description = "Contains the response of an HTTP request."
categories = ["API", "Type"]
+++

`type HttpResponse = {Body: Variant?, Cookies: Cookies, Headers: HttpHeaders, StatusCode: int, StatusMessage: string, Success: bool}`

The **HttpResponse** type is a table that contains the response of a
request. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Success | [bool](/api/types/bool) | Whether the request succeeded. True if StatusCode between 200 and 299. |
| StatusCode | [int](/api/types/int) | The HTTP status code of the response. |
| StatusMessage | [string](/api/types/string) | A readable message corresponding to the StatusCode. |
| Headers | [HttpHeaders](/api/types/HttpHeaders) | A set of response headers. |
| Cookies | [Cookies](/api/types/Cookies) | Cookies parsed from the Set-Cookie header. |
| Body | any? | The decoded body of the response. |