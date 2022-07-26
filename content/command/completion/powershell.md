+++
weight = 1
title = "powershell"
description = "Generate autocompletion script for powershell."
categories = ["Command", "Subcommand"]
+++

`rbxmk completion powershell`

Generate the autocompletion script for powershell.

To load completions in your current shell session:

```powershell
rbxmk completion powershell | Out-String | Invoke-Expression
```

To load completions for every new session, add the output of the above
command to your powershell profile.