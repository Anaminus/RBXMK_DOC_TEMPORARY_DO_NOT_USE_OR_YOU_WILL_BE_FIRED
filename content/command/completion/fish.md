+++
weight = 1
title = "fish"
description = "Generate autocompletion script for fish."
categories = ["Command", "Subcommand"]
+++

`rbxmk completion fish`

Generate the autocompletion script for the fish shell.

To load completions in your current shell session:

```fish
rbxmk completion fish | source
```

To load completions for every new session, execute once:

```fish
rbxmk completion fish > ~/.config/fish/completions/rbxmk.fish
```

You will need to start a new shell for this setup to take effect.