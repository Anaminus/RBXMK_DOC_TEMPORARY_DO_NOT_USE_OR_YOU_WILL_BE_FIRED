+++
weight = 20
title = "Overview"
description = "Overview of rbxmk."
titleIcon = "fas fa-book"
+++

# Command-line interface

rbxmk is a single executable, to be run within a [command-line interface][cli].

{{<alert type="info">}}

It is recommended that you are familar with the command-line interface (CLI). In
addition to the above resource, the following video provides an introduction to
CLIs:

[Command Line Interface (CLI) For Beginners][cli-video]

[cli-video]: https://www.youtube.com/watch?v=mUXVBMhr7Xg

{{</alert>}}

The [command reference](command) pages provide information about the rbxmk
executable, and the commands that can be run.

The [API reference](api) pages provide documentation of the API available in
rbxmk's Lua environment.

The same information is provided by the executable itself. Running `rbxmk` with
no other options will display a help message, which includes all the available
commands that can be run. The [help](command/help) command will display help for
any command. In addition, the `--help` or `-h` flag can be added to any command
to display help for that command. The [doc](command/doc) command provides
information for a number of rbxmk-related topics, including the Lua API.

[cli]: https://en.wikipedia.org/wiki/Command-line_interface
