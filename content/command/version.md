+++
weight = 1
title = "version"
description = "Display the version."
categories = ["Command"]
+++

`rbxmk version`

The **version** command displays the current version of rbxmk. The result
is formatted according to [semantic versioning](https://semver.org/).

# Flags

----

## format

`-f, --format string` `(default: "text")`

Format of the version output. Available formats are "text", "json".

## verbose

`-v, --verbose count` `(default: "0")`

Increase verbosity level by 1 for each time the flag is specified. Default is
level 0. Each level appends the following information:

| Level | Description |
| --- | --- |
| 0 | Includes program version. |
| 1 | Includes basic build information. |
| 2 | Includes detailed build information. |
| 3 | Includes module information. |