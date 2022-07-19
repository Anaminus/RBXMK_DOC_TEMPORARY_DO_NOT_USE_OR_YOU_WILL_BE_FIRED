+++
weight = 110
title = "path"
+++

The **path** library provides functions that handle file paths.

| Item | Kind | Description |
| --- | --- | --- |
| [clean](#clean) | Function | Cleans up a file path. |
| [expand](#expand) | Function | Expands predefined file path variables. |
| [join](#join) | Function | Joins a number of file paths together. |
| [split](#split) | Function | Splits a file path into its components. |

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
| `$script_directory`, `$script_dir`, `$sd` | The directory of the currently running script. Empty for stdin. |
| `$root_script_directory`, `$root_script_dir`, `$rsd` | The directory of the first running script. Empty for stdin. |
| `$working_directory`, `$working_dir`, `$wd` | The current working directory. |
| `$temp_directory`, `$temp_dir`, `$tmp` | The directory for temporary files. |

## join

 `path.join(...: string): string`

The **join** function joins each *path* element into a single path,
separating them using the operating system's path separator. This also cleans up
the path.

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