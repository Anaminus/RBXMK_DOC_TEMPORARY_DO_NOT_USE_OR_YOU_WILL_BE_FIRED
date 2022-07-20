+++
weight = 110
title = "rbxassetid"
+++

The **rbxassetid** library provides an interface to assets on the Roblox
website.

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [read](#read) | Function | Reads data from a rbxassetid in a certain format. |
| [write](#write) | Function | Writes data to a rbxassetid in a certain format. |

</div>

# Functions

----

## read

 `rbxassetid.read(options: RbxAssetOptions): (value: any)`

The **read** function downloads an asset according to the given [options](type:RbxAssetOptions). Returns the content of the asset
corresponding to AssetId, decoded according to Format.

Throws an error if a problem occurred while downloading the asset.

## write

 `rbxassetid.write(options: RbxAssetOptions)`

The **write** function uploads to an existing asset according to the given
[options](type:RbxAssetOptions). The Body is encoded according to
Format, then uploaded to AssetId. AssetId must be the ID of an existing
asset.

Throws an error if a problem occurred while uploading the asset.