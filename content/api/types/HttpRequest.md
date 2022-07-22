+++
weight = 1
title = "HttpRequest"
description = "Represents a pending HTTP request."
categories = ["API", "Type"]
+++

The **HttpRequest** type represents a pending HTTP request.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [Cancel](#cancel) | Method | Cancels the pending request. |
| [Resolve](#resolve) | Method | Returns the response to the request. |

</div>

# Methods

----

## Cancel

 `HttpRequest:Cancel()`

The **Cancel** method cancels the pending request.

## Resolve

 `HttpRequest:Resolve(): (resp: HttpResponse)`

The **Resolve** method blocks until the request has finished, and returns
the response. Throws an error if a problem occurred while resolving the
request.