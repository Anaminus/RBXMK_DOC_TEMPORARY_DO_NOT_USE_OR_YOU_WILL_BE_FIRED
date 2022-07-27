+++
weight = 1
title = "plugin"
description = "Run a dump format plugin."
categories = ["Command", "Subcommand"]
+++

`rbxmk dump plugin 	FILE
`

The **plugin** command enables the generation of a custom dump format. The
command receives a file to be executed as a Lua script.

```bash
rbxmk dump plugin script.lua
```

If `-` is given as the file, then the script will be read from
standard input instead.

```bash
echo 'print("hello world!")' | rbxmk dump plugin -
```

The script receives as arguments a table and a function.

```lua
local dump, write = ...
```

The table contains a complete description of the rbxmk Lua environment. The
structure of the table matches the structure of the `json` dump
format.

The function is used to build the output. It receives any number of values,
converts them to strings, and concatenates them directly to the result.

```lua

-- List all libraries.
local dump, write = ...
for _, library in ipairs(dump.Libraries) do
	write(library.Name, "\n")
end

```

After the script finishes, the result is written to standard output.

Unlike the run command, the script runs in a limited environment that
includes only the following libraries:

- base
- program
- math
- string
- table

# Flags

----

## help

`-h, --help`

**Default:** `false`

Displays help for the command.