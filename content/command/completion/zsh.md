+++
weight = 1
title = "zsh"
description = "Generate autocompletion script for zsh."
categories = ["Command", "Subcommand"]
+++

`rbxmk completion zsh`

Generate the autocompletion script for the zsh shell.

If shell completion is not already enabled in your environment you will need
to enable it. You can execute the following once:

```bash
echo "autoload -U compinit; compinit" >> ~/.zshrc
```

To load completions for every new session, execute once:

**Linux:**

```bash
rbxmk completion zsh > "${fpath[1]}/_rbxmk"
```

**macOS:**

```bash
rbxmk completion zsh > /usr/local/share/zsh/site-functions/_rbxmk
```

You will need to start a new shell for this setup to take effect.

# Flags

----

## help

`-h, --help`

**Default:** `false`

Displays help for the command.

## no-descriptions

`--no-descriptions`

**Default:** `false`

Disables completion descriptions.