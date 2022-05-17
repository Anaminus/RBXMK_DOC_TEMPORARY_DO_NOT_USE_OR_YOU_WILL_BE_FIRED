+++
weight = 40
title = "API reference"
description = "Reference for the rbxmk Lua environment."
titleIcon = "fas fa-list"
+++

<p style="text-align:right"><i>API: Application Programming Interface</i></p>

{{<warn-v0>}}

[Lua](https://lua.org/) scripts are used to perform actions in rbxmk. By
convention only, scripts run with rbxmk have the `.rbxmk.lua` extension.

The Lua API for rbxmk is designed to closely resemble Roblox's Lua API. The
current Lua implementation is based on 5.1.

The API can be divided into the following categories:

- [**Library**](api/libraries): A set of modifications to the Lua environment.
- [**Type**](api/types): The type of a value.
- [**Format**](api/formats): A method of encoding and decoding types.
