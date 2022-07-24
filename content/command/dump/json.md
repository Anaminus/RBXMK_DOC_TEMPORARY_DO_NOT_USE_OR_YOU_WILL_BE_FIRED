+++
weight = 1
title = "json"
description = "General JSON format."
categories = ["Command", "Subcommand"]
+++

`rbxmk dump json`

The **json** dump format describes the API of the Lua environment in JSON
format.

The top-level value is a JSON object. The **Version** field is a number
that signals the structure of the JSON format, and will be present in all
versions of the format.

Run `rbxmk doc "Commands/dump/json:Version 0"` for a detailed
description of the structure.

# Flags

----

## indent

`--indent string` `(default: "\t")`

Specifies the spacing used to indent the JSON output. If empty, the output will
be minified (use --indent="" to specify an empty string).