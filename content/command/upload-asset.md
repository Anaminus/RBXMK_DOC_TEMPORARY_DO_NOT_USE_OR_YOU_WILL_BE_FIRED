+++
weight = 1
title = "upload-asset"
description = "Upload an asset."
categories = ["Command"]
+++

`rbxmk upload-asset 	[ FLAGS ] [ --id INT ] PATH
`

The **upload-asset** command uploads an asset to the roblox website.

The `--id` flag specifies the ID of the asset to upload. If not
specified, then a new asset will be created, and the ID of the asset will be
returned.

The first non-flag argument is the path to a file to read from, which is
required. If the path is "-", then the file will be read from standard
input.

Each cookie flag appends to the list of cookies that will be sent with the
request. Such flags can be specified any number of times.

# Flags

----

## cookie-var

`--cookie-var function`

Append a cookie from environment variable \`var\`. The content is formatted as
a number of Set-Cookie headers. Can be given any number of times.

## cookies-file

`--cookies-file function`

Append cookies from the file located at \`path\`. The file is formatted as a
number of [Set-Cookie](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie)
headers. Can be given any number of times.

## cookies-from

`--cookies-from function`

Append cookies from a known \`location\`. See the documentation of [Cookie.from](/api/types/Cookie#from) for a list of locations. Can be given
any number of times.

## file-format

`--file-format string`

The format to decode the file as. Defaults to --format.

## format

`--format string`

**Default:** `"bin"`

The format to encode the asset as.

## id

`--id int64`

**Default:** `"0"`

The ID of the asset to download (required).