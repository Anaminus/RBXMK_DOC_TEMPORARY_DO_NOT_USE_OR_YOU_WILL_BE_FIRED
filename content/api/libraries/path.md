+++
weight = 110
title = "path"
description = "Handles file paths."
categories = ["API", "Library"]
+++

The **path** library provides functions that handle file paths.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [clean](#clean) | Function | Cleans up a file path. |
| [expand](#expand) | Function | Expands predefined file path variables. |
| [join](#join) | Function | Joins a number of file paths together. |
| [rel](#rel) | Function | Produces a relative path. |
| [split](#split) | Function | Splits a file path into its components. |

</div>

# Functions

----

## clean

 `path.clean(path: string): string`

The **clean** function returns the shortest path equivalent to
*path*. Separators are replaced with the OS-specific path separator.

## expand

 `path.expand(path: string): string`

The **expand** function scans *path* for certain variables of the
form `$var` or `${var}` an expands them. The following
variables are expanded:

| Variable | Description |
| --- | --- |
| `$script_name`, `$sn` | The base name of the currently running script. Empty for stdin. |
| `$script_directory`, `$script_dir`, `$sd` | The directory of the currently running script. Expands to the working directory for stdin. Causes an error if the working directory could not be located. |
| `$root_script_directory`, `$root_script_dir`, `$rsd` | The directory of the first running script. Expands to the working directory for stdin. Causes an error if the working directory could not be located. |
| `$working_directory`, `$working_dir`, `$wd` | The current working directory. Causes an error if the working directory could not be located. |
| `$temp_directory`, `$temp_dir`, `$tmp` | The directory for temporary files. Causes an error if a temporary directory could not be located. |

Other variables cause an error to be thrown.

## join

 `path.join(...: string): string`

The **join** function joins each *path* element into a single path,
separating them using the operating system's path separator. This also cleans up
the path.

## rel

 `path.rel(basePath: string, targetPath: string): string?`

The **rel** function returns a relative path that is equivalent to
*targetPath* when joined with *basePath*, such that following
equivalence is true:

```lua
path.clean(targetPath) == path.join(basePath, path.rel(basePath, targetPath))
```

[path.clean](/api/libraries/path#clean) is called on the result. Returns nil
if *targetPath* cannot be made relative to *basePath*.

## split

 `path.split(path: string, ...: string): (...: string)`

The **split** function returns the components of a file path.

| Component | `project/scripts/main.script.lua` | Description |
| --- | --- | --- |
| `base` | `main.script.lua` | The file name; the last element of the path. |
| `dir` | `project/scripts` | The directory; all but the last element of the path. |
| `ext` | `.lua` | The extension; the suffix starting at the last dot of the last element of the path. |
| `fext` | `.script.lua` | The format extension, as determined by registered formats. |
| `fstem` | `main` | The base without the format extension. |
| `stem` | `main.script` | The base without the extension. |

A format extension depends on the available formats. See [Formats](formats.md) for more information.