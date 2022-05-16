+++
weight = 20
title = "Overview"
description = "Overview of rbxmk."
titleIcon = "fas fa-book"
+++

# What is Roblox?
From the [Roblox website](https://corp.roblox.com/):

> Roblox’s mission is to bring the world together through play. We enable anyone
> to imagine, create, and have fun with friends as they explore millions of
> immersive 3D experiences, all built by a global community of developers.

# What is Lua?
From the [Lua website](https://www.lua.org/about.html):

> Lua is a powerful, efficient, lightweight, embeddable scripting language. It
> supports procedural programming, object-oriented programming, functional
> programming, data-driven programming, and data description.

# What is rbxmk?
rbxmk is a command-line tool for processing data to aid with the game
development workflow, tailored specifically for Roblox. rbxmk has full
capability for reading and writing Roblox's proprietary file formats, including
**rbxl**, **rbxlx**, **rbxm**, and **rbxmx**. It also provides operations for
moving data through a number of interfaces, such as the file system, the
clipboard, the Roblox website, or any generic network resource.

## Common interface
rbxmk is built as an executable program to be run within a [command-line
interface][cli] (CLI). A CLI is preferred because it is cross-platform; every
operating system under the sun provides one. In addition to enabling manual work
and one-off snippets, this also makes rbxmk suitable for automated tasks, such
as continuous integration and build automation.

[Command reference <span class="icon"><i class="fas fa-arrow-right"></i></span></a>](command)

[cli]: https://en.wikipedia.org/wiki/Command-line_interface

## Familiar environment
Most of rbxmk's behavior is facilitated through Lua scripts. Lua was chosen
because it enables an environment that is familiar to developers on Roblox.

[API reference <span class="icon"><i class="fas fa-arrow-right"></i></span></a>](api)

## Instance management
rbxmk provides an API for managing instances that closely resembles Roblox's
instances. In addition to getting and setting properties, the usual methods for
navigating instance trees are implemented, including Parent, FindFirstChild, and
GetChildren.

Also implemented are supplementary operations for handling attributes and tags.
Additionally, rbxmk implements Roblox's pivot system, which enables easy
placement of 3D models.

[Instances <span class="icon"><i class="fas fa-arrow-right"></i></span></a>](overview/instances)

## Forward-compatible
Roblox's API is always changing. To keep up with these changes, rbxmk is
designed to be flexible, adaptable, and customizable.

There are no assumptions: The rbxmk API is able to function without any
knowledge of Roblox. However, to improve convenience and familiarity,
**descriptors** can be applied to augment the rbxmk environment. The official
API dumps provided by Roblox can be used to make rbxmk more Roblox-like, or the
user can supply their own descriptors, customized to suit their needs.

[Descriptors <span class="icon"><i class="fas fa-arrow-right"></i></span></a>](overview/descriptors)

## Configurable
Configuration files can be used to configure the behavior of rbxmk. Files are
read and merged at various scopes: per computer, per user, per project, and
more.

[Configuration <span class="icon"><i class="fas fa-arrow-right"></i></span></a>](overview/configuration)

## Safe and secure
rbxmk provides a detailed permissions system that can reduce or eliminate the
impact of malicious third-party scripts, while remaining adaptable to the user's
needs, and curating a trustworthy ecosystem.

[Permissions <span class="icon"><i class="fas fa-arrow-right"></i></span></a>](overview/permissions)

## First-party integration
Sub-projects for integrating rbxmk into your DevOps workflow are available:

- [setup-rbxmk](https://github.com/anaminus/setup-rbxmk) for GitHub Actions.
- [setup-rbxmk]() for GitLab CI.

[Automation <span class="icon"><i class="fas fa-arrow-right"></i></span></a>](overview/automation)

# Similar projects

- [Rojo](https://rojo.space/): Syncing between Roblox Studio and the file system.
	- The [rojo.rbxmk.lua]() script can be used to build Rojo projects with
	  rbxmk.
- [Remodel](https://github.com/rojo-rbx/remodel): Scriptable Roblox multitool.
	- The [rbxmk vs Remodel](overview/remodel) page compares the two projects.
