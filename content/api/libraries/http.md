+++
weight = 110
title = "http"
+++

The **http** library provides an interface to resources on the network via
HTTP.

| Item | Kind | Description |
| --- | --- | --- |
| [request](#request) | Function | Begins an HTTP request. |

# Functions

----

## request

 `http.request(options: HttpOptions): (req: HttpRequest)`

The **request** function begins a request with the specified [options](type:HttpOptions). Returns a [request object](type:HttpRequest) that may be [resolved](type:HttpRequest.Resolve) or [canceled](type:HttpRequest.Cancel). Throws an error if the request
could not be started.