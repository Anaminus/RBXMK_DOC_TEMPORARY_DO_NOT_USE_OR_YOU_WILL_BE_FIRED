+++
weight = 110
title = "os"
description = "Extensions to the standard os library."
categories = ["API", "Library"]
+++

The **os** library is an extension to the standard library.

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [getenv](#getenv) | Function | Gets an environment variable. |

</div>

# Functions

----

## getenv

 `os.getenv(name: string?): string?|{[string]: string}`

The **getenv** function returns the value of the *name* environment
variable, or nil if no such value is defined. If *name* is not specified,
then a table of environment variable names mapped to values is returned.