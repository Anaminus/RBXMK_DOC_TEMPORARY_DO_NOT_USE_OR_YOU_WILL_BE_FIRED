+++
weight = 5
title = "Quick start"
description = "Getting started with rbxmk."
titleIcon = "fas fa-power-off"
+++


This page provides steps for quickly getting started with rbxmk.

{{<alert type="info">}}

Used to Remodel? check out the [comparison guide](overview/remodel).

{{</alert>}}

# Steps
<p class="is-size-4 is-italic">Give a classic place a fresh look.</p>

These steps use Windows for their examples. See the [Installation](installation)
page for instructions on how to install rbxmk for other operating systems.

## 1) Install rbxmk
{{<noimpl>}}
Download the [latest Windows installer][installer], then open it and follow the
prompts. This will install rbxmk to your computer, and make it possible to run
from a terminal.

[installer]: https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-windows-setup.zip

## 2) Get a terminal going
rbxmk is a command-line program, which requires to a terminal to run.

1. Click the **Start menu**.
2. In the menu's search box, type `cmd`, then press the **Enter** key.

A Command Prompt window will appear. This is a terminal that will let you run
commands.

{{<alert type="info">}}

It is recommended that you are familar with the [command-line interface][cli]
(CLI). The following video provides an introduction:

[Command Line Interface (CLI) For Beginners][cli-video]

[cli]: https://en.wikipedia.org/wiki/Command-line_interface
[cli-video]: https://www.youtube.com/watch?v=mUXVBMhr7Xg

{{</alert>}}

If desired, your preferred terminal can be used instead.

## 3) Verify the installation
In the terminal, type the following command:

```batch
rbxmk version
```

If rbxmk was installed correctly, running this command will print the installed
version of rbxmk. For example, the latest version is **0.9.1**.

## 4) Find a suitable place to work
Direct the terminal to work in a new folder created on the desktop with the
terminal's `mkdir` and `cd` commands:

```batch
mkdir %USERPROFILE%\Desktop\ExampleProject
cd %USERPROFILE%\Desktop\ExampleProject
```

The `mkdir` command creates the "ExampleProject" folder on the desktop. The `cd`
command changes the working directory of the terminal to the created folder.

## 5) Create a new script
The terminal's `echo` command will output its input. The `>` operator will write
the output of a command to a file. Use these to create a new script file:

```batch
echo print("Hello, world!") > script.lua
```

## 6) Run the script
rbxmk's [run][run] command is used to run scripts.

```batch
rbxmk run script.lua
```

The text `Hello, world!` will appear in the terminal.

[run]: command/run

## 7) Download the latest descriptors
{{<noimpl>}}
Using the latest [Descriptors][descriptors] from Roblox will allow rbxmk to be
used more easily.

```batch
rbxmk update-descriptors
```

[descriptors]: overview/descriptors

## 8) Download some assets to work on
Use the [download-asset][download-asset] command to get some assets from the
Roblox website.

```batch
rbxmk download-asset --id 1818 Crossroads.rbxl
rbxmk download-asset --id 185687363 Tower.rbxm
```

This will download the [Crossroads][crossroads] place, and the [Observation
Tower][tower] model.

[download-asset]: command/download-asset
[crossroads]: https://www.roblox.com/games/1818/Classic-Crossroads
[tower]: https://www.roblox.com/library/185687363/Observation-Tower

## 9) Edit the script
{{<noimpl reason="Pivot API">}}
Use your preferred editor to edit `script.lua`. Write a script that adds the
tower model to the place:

```lua
-- Load the place.
local game = fs.read("Crossroads.rbxl")

-- Remove the old model.
local Workspace = game:GetService("Workspace")
local oldTower = Workspace:FindFirstChild("Tower")
if oldTower then
	oldTower:Destroy()
end

-- Insert the new model.
local tower = fs.read("Tower.rbxm")
tower:PivotTo(CFrame.new(-80, 1.2, -80))
tower.Parent = Workspace

-- Save the place.
fs.write("NewCrossroads.rbxl", game)
```

## 10) Run the edited script
Back in the terminal, run the script again:

```batch
rbxmk run script.lua
```

This will create the `NewCrossroads.rbxl` file, which is the same as the
downloaded place, but has the old tower model replaced with the downloaded tower
model.

# Going forward
The [Overview](overview) page provides an overview of the rbxmk project and
related concepts.

The [Command reference](command) pages provide information about the rbxmk
executable, and the commands that can be run.

The [API reference](api) pages provide documentation of the API available in
rbxmk's Lua environment.