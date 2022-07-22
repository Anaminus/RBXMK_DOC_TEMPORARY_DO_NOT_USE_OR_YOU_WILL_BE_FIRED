+++
weight = 1
title = "FileInfo"
description = "The metadata of a file."
categories = ["API", "Type"]
+++

`type FileInfo = {IsDir: bool, ModTime: int64, Name: string, Size: int64}`

The **FileInfo** type is a table that contains metadata about a file. It
has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Name | string | The base name of the file. |
| IsDir | boolean | Whether the file is a directory. |
| Size | number | The size of the file, in bytes. |
| ModTime | number | The modification time of the file, in Unix time. |