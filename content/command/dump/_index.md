+++
weight = 1
title = "dump"
description = "Dump the script API."
categories = ["Command"]
+++

`rbxmk dump 	FORMAT
`

The **dump** command dumps the API of the rbxmk Lua environment in a
specified format.

# Flags

----

## help

`-h, --help`

**Default:** `false`

Displays help for the command.

# Subcommands

----

<div class="api-list one">

| Subcommand | Description |
| --- | --- |
| [fragments](fragments) | List of document fragment paths. |
| [json](json) | General JSON format. |
| [plugin](plugin) | Run a dump format plugin. |
| [selene](selene) | Selene TOML format. |

</div>