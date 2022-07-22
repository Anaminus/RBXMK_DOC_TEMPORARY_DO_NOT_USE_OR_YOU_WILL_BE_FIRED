+++
weight = 110
title = "http"
description = "An interface to resources via HTTP."
categories = ["API", "Library"]
+++

The **http** library provides an interface to resources on the network via
HTTP.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [request](#request) | Function | Begins an HTTP request. |

</div>

# Functions

----

## request

 `http.request(options: HttpOptions): (req: HttpRequest)`

The **request** function begins a request with the specified [options](/api/types/HttpOptions). Returns a [request object](/api/types/HttpRequest) that may be [resolved](/api/types/HttpRequest#resolve) or [canceled](/api/types/HttpRequest#cancel). Throws an error if the request
could not be started.