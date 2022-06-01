+++
title = "rbxmk - A tool for processing Roblox files"
description = "A tool for processing Roblox files."
+++

<div class="columns is-centered">
<div class="column is-narrow">
<div class="logo"><img src="images/logoTouch.png" alt="rbxmk logo"/><span>rbxmk</span></div>
</div>
</div>
<div class="columns">
<div class="column has-text-centered is-size-4 is-size-5-touch">

**rbxmk** is a tool for processing Roblox files.

Whether your project is a game, plugin, module, or whatever, rbxmk is essential
for your workflow.

</div>
</div>
<div class="columns is-centered is-size-4 is-size-5-touch">
	<div class="column is-narrow has-text-centered"><a class="is-pretty-link" href="quickstart"><span class="icon-text"><span class="icon"><i class="fas fa-power-off"></i></span><span>Get started</span></span></a></div>
	<div class="column is-narrow has-text-centered"><a class="is-pretty-link" href="installation"><span class="icon-text"><span class="icon"><i class="fas fa-download"></i></span><span>Download</span></span></a></div>
</div>
<div class="showcase container is-max-desktop">

<div class="columns is-vcentered is-centered">
<div class="column is-two-fifths is-size-5 is-size-6-touch">

Through a familiar Lua API, data can be received, transformed, and sent in
whatever way you need.

</div>
<div class="column is-three-fifths is-size-6 is-size-7-touch">

```lua
local url = clipboard.read("txt")
local id = tonumber(url:match("%d+"))
if id then
	local asset = rbxassetid.read({
		AssetId = id,
		Format = "rbxm",
	})
	clipboard.write(asset, "rbxm")
end
```

</div>
</div>

<div class="columns is-vcentered is-centered">
<div class="column is-two-fifths is-size-5 is-size-6-touch" style="order:2">

Drill into your models, surgically pick them apart, and recombine them.

</div>
<div class="column is-three-fifths is-size-6 is-size-7-touch" style="order:1">

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

<div class="columns is-vcentered is-centered">
<div class="column is-two-fifths is-size-5 is-size-6-touch">

{{<noimpl reason="tags, pivots">}}
First-class support for all data types, as well as attributes, tags, and pivots.

</div>
<div class="column is-three-fifths is-size-6 is-size-7-touch">

```lua
local position = model:GetAttribute("Position")
if typeof(position) ~= "Vector3" then
	position = Vector3.zero
end
model:PivotTo(CFrame.new(position))
```

</div>
</div>

<div class="hero is-cli is-medium">
<div class="hero-body">
<div class="title is-size-3 is-size-4-touch"><span class="icon-text"><span class="icon is-hidden-mobile" style="padding-right: 0.5em"><i class="fas fa-terminal"></i></span><span>Command-line</span></span></div>
<div class="subtitle is-size-5 is-size-6-touch">A common interface for both manual and automated work.</div>
</div>
</div>

<div class="hero is-info is-medium has-text-right">
<div class="hero-body">
<div class="title is-size-3 is-size-4-touch"><span class="icon-text"><span class="icon is-hidden-mobile" style="padding-right: 0.5em"><i class="fas fa-book"></i></span><span>Rich documentation</span></span></div>
<div class="subtitle is-size-5 is-size-6-touch">Has a complete reference built-in.</div>
</div>
</div>

<div class="hero is-success is-medium">
<div class="hero-body">
{{<noimpl>}}
<div class="title is-size-3 is-size-4-touch"><span class="icon-text"><span class="icon is-hidden-mobile" style="padding-right: 0.5em"><i class="fas fa-download"></i></span><span>Fast installation</span></span></div>
<div class="subtitle is-size-5 is-size-6-touch">With a streamlined installer, getting started is a breeze.</div>
</div>
</div>

<div class="hero has-text-centered">
<div class="hero-body">
<div class="title is-size-3 is-size-4-touch"><a class="is-pretty-link" href="quickstart"><span class="icon-text"><span class="icon"><i class="fas fa-power-off"></i></span><span>Let's go!</span></span></a></div>
</div>
</div>

</div>
