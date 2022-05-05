+++
title = "rbxmk - A tool for processing Roblox files"
description = "A tool for processing Roblox files."
+++

<div class="columns is-centered">
<div class="column is-narrow">
<div class="columns is-centered">
<div class="column is-narrow">
<div class="logo"><img src="images/logoTouch.png" alt="rbxmk logo"/><span>rbxmk</span></div>
</div>
</div>
<div class="columns is-centered">
<div class="column is-narrow">

**rbxmk** is a tool for processing [Roblox][roblox] files.

</div>
</div>
</div>
</div>
<!-- <hr> -->
<div class="columns is-vcentered is-centered">
<div class="column is-half">

Through a familiar [Lua][lua] API, receive data, transform it, and send it where
it needs to go.

</div>
<div class="column is-half">

```lua
local url = clipboard.read("txt")
local id = tonumber(url:match("%d+"))
if id then
	local asset = rbxassetid.read({
		AssetID = id,
		Format = "rbxm",
	})
	clipboard.write(asset, "rbxm")
end
```

</div>
</div>
<!-- <hr> -->
<div class="columns is-vcentered is-centered">
<div class="column is-half" style="order:2">

Drill into your models, surgically pick them apart, and recombine them to suit
your needs.

</div>
<div class="column is-half" style="order:1">

```lua
local game = fs.read("place.rbxl")
local models = game:Descend("Workspace", "Models")
for i, model in ipairs(models:GetChildren()) do
	local fileName = model.Name .. ".rbxm"
	fs.write(path.join("models", fileName))
end
```

</div>
</div>
<!-- <hr> -->
<div class="columns is-vcentered is-centered">
<div class="column is-half">

First-class support for most data types, as well as attributes, tags, and
pivots.

</div>
<div class="column is-half">

```lua
local position = model:GetAttribute("Position")
if typeof(position) ~= "Vector3" then
	position = Vector3.zero
end
model:PivotTo(CFrame.new(position))
```

</div>
</div>
<!-- <hr> -->
<div class="columns is-centered">
<div class="column .container" style="text-align:center">
<a href="quickstart" style="font-size:2em">Let's get started!</a>
</div>
</div>

[roblox]: https://corp.roblox.com
[lua]: https://lua.org
