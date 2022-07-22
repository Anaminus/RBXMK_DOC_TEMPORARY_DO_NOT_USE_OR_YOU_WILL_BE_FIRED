+++
weight = 1
title = "DirEntry"
description = "An entry of a directory."
categories = ["API", "Type"]
+++

`type DirEntry = {IsDir: bool, Name: string}`

The **DirEntry** type is a table that contains a file entry of a
directory. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Name | string | The base name of the file. |
| IsDir | boolean | Whether the file is a directory. |