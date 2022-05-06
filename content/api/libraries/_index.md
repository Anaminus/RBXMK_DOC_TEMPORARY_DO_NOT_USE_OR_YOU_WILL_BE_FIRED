+++
weight = 10
title = "Libraries"
description = "Library reference."
+++

The Lua environment provided by rbxmk is packaged as a list of libraries.

In rbxmk, a **library** is most accurately described as **a set of modifications
to the Lua environment**. Some libraries group functions under a single table as
normally expected, while others add a number of functions directly to the global
table. Some libraries add a number of tables, and others merge with tables that
already exist. Libraries are loaded in ascending order by their priority value.

The following libraries are available:

<div class="api-list">

Library                                | Description
---------------------------------------|------------
[base](api/libraries/base)             | The Lua 5.1 standard library, abridged.
[program](api/libraries/program)       | Values related to the running program.
[rbxmk](api/libraries/rbxmk)           | An interface to the rbxmk engine, and the rbxmk environment.
[roblox](api/libraries/roblox)         | An environment emulating the Roblox Lua API.
[clipboard](api/libraries/clipboard)   | An interface to the clipboard.
[fs](api/libraries/fs)                 | An interface to the file system.
[http](api/libraries/http)             | An interface to network resources.
[math](api/libraries/math)             | Extensions to the standard math library.
[os](api/libraries/os)                 | Extensions to the standard os library.
[path](api/libraries/path)             | File path manipulation.
[rbxassetid](api/libraries/rbxassetid) | An interface to Roblox assets.
[string](api/libraries/string)         | Extensions to the standard string library.
[sym](api/libraries/sym)               | Symbols for accessing instance metadata.
[table](api/libraries/table)           | Extensions to the standard table library.
[types](api/libraries/types)           | Fallbacks for constructing certain types.

</div>

# Filtering
The [run](command/run) and [interactive](command/interactice) commands have a
`--libraries` flag, which allows the user to include and exclude libraries.

A library can have a number of [types](api/types) as dependencies. When the
library is included, it will pull these types into the environment. For example,
The [roblox](api/libraries/roblox) library depends on the [CFrame](types/CFrame)
type, so including it will also include the `CFrame` table into the global
environment.

Conversely, if no included libraries depend on a type, then that type will *not*
be included.
