+++
weight = 1
title = "RbxAssetOptions"
description = "Specifies the options of an asset request."
categories = ["API", "Type"]
+++

`type RbxAssetOptions = {AssetId: int64, Body: any?, Cookies: Cookies?, Format: FormatSelector}`

The **RbxAssetOptions** type is a table that specifies the options of a
request to an asset on the Roblox website. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| AssetId | [int64](/api/types/int64) | The ID of the asset to request. |
| Cookies | [Cookies](/api/types/Cookies)? | Optional cookies to send with requests, usually used for authentication. |
| Format | [FormatSelector](/api/types/FormatSelector) | The format used to encode or decode an asset. |
| Body | any? | The body of an asset, to be encoded by the specified format. |