+++
weight = 1
title = "download-asset"
description = "Download an asset."
categories = ["Command"]
+++

`rbxmk download-asset 	[ FLAGS ] --id INT [ PATH ]
`

The **download-asset** command downloads an asset from the roblox
website.

The `--id` flag, which is required, specifies the ID of the asset
to download.

The first non-flag argument is the path to a file to write to. If not
specified, then the file will be written to standard output.

Each cookie flag appends to the list of cookies that will be sent with the
request. Such flags can be specified any number of times.

# Flags

----

## cookie-var

`--cookie-var var`

Append a cookie from environment variable \`var\`. The content is formatted as
a number of Set-Cookie headers. Can be given any number of times.

## cookies-file

`--cookies-file path`

Append cookies from the file located at \`path\`. The file is formatted as a
number of [Set-Cookie](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie)
headers. Can be given any number of times.

## cookies-from

`--cookies-from location`

Append cookies from a known \`location\`. See the documentation of [Cookie.from](/api/types/Cookie#from) for a list of locations. Can be given
any number of times.

## file-format

`--file-format string`

The format to encode the file as. Defaults to --format.

## format

`--format string`

**Default:** `"bin"`

The format to decode the asset as.

## id

`--id int64`

**Default:** `0`

The ID of the asset to download (required).