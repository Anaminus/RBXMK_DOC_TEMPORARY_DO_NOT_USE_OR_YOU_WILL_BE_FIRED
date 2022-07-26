+++
weight = 1
title = "run"
description = "Execute a script."
categories = ["Command"]
+++

`rbxmk run 	[ FLAGS ] FILE [ VALUE... ]
`

The **run** command receives a file to be executed as a Lua script.

```bash
rbxmk run script.lua
```

If `-` is given as the file, then the script will be read from
standard input instead.

```bash
echo 'print("hello world!")' | rbxmk run -
```

The remaining arguments are Lua values to be passed to the file. Numbers,
bools, and nil are parsed into their respective types in Lua, and any other
value is interpreted as a string.

```bash
rbxmk run script.lua true 3.14159 hello!
```

Including a bare \`--\` will cause the run command to stop interpreting flags,
enabling them to be passed to the script. Note that such flags will be passed as
regular strings.

```bash

rbxmk run script.lua -- --help
# Passes "--help" string.

```

Within the script, these arguments can be received from the `...`
operator.

```lua
local arg1, arg2, arg3 = ...
```

The `--desc-*` flags set the `rbxmk.globalDesc` field.
They also set the `Enum` global variable to the enums generated from
the descriptor.

# Flags

----

## allow-insecure-paths

`--allow-insecure-paths`

**Default:** `false`

Disable path restrictions, allowing scripts to access any path in the file
system.

## debug

`--debug`

**Default:** `false`

Display stack traces when an error occurs.

## desc-file

`--desc-file path`

Include the file located at \`path\` as a global descriptor. May be specified
any number of times. Multiple descriptors are merged in the order specified.

## desc-latest

`--desc-latest`

**Default:** `false`

Download and start with the latest API dump as the global descriptor.

## desc-patch

`--desc-patch path`

Include the file located at \`path\` as a patch to the global descriptor. May
be specified any number of times. Multiple patches are applied in the order
specified.

## include-root

`--include-root path`

**Default:** `[]`

Mark a \`path\` as an accessible root directory. May be specified any number of
times.

## libraries

`--libraries list`

**Default:** `[]`

A comma-separated \`list\` of libraries to include or exclude. A name prefixed
with "+" or nothing is included, and a name prefixed with "-" is excluded. If
the name is "\*", then the state is applied to all libraries. States are applied
in order.