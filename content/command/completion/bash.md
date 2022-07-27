+++
weight = 1
title = "bash"
description = "Generate autocompletion script for bash."
categories = ["Command", "Subcommand"]
+++

`rbxmk completion bash`

Generate the autocompletion script for the bash shell.

This script depends on the 'bash-completion' package. If it is not installed
already, you can install it via your OS's package manager.

To load completions in your current shell session:

```bash
source <(rbxmk completion bash)
```

To load completions for every new session, execute once:

**Linux:**

```bash
rbxmk completion bash > /etc/bash_completion.d/rbxmk
```

**macOS:**

```bash
rbxmk completion bash > /usr/local/etc/bash_completion.d/rbxmk
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