+++
weight = 101
title = "rbxmk"
description = "An interface to the rbxmk engine, and the rbxmk environment."
categories = ["API", "Library"]
+++

The **rbxmk** library contains functions related to the rbxmk engine.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [globalAttrConfig](#globalattrconfig) | Field | Get or set the global AttrConfig. |
| [globalDesc](#globaldesc) | Field | Get or set the global descriptor. |
| [decodeFormat](#decodeformat) | Function | Deserialize data from bytes. |
| [encodeFormat](#encodeformat) | Function | Serialize data into bytes. |
| [formatCanDecode](#formatcandecode) | Function | Check whether a format decodes into a type. |
| [get](#get) | Function | Gets the property of an instance. |
| [loadFile](#loadfile) | Function | Load the content of a file as a function. |
| [loadString](#loadstring) | Function | Load a string as a function. |
| [propType](#proptype) | Function | Gets the unreflected type of an instance property. |
| [runFile](#runfile) | Function | Run a file as a Lua chunk. |
| [runString](#runstring) | Function | Run a string as a Lua chunk. |
| [set](#set) | Function | Sets the property of an instance. |
| [Enum](enum) | Struct | Collection of rbxmk-defined enums. |

</div>

# Fields

----

## globalAttrConfig

 `rbxmk.globalAttrConfig: AttrConfig?`

The **globalAttrConfig** field gets or sets the global AttrConfig. Most
items that utilize an AttrConfig will fallback to the global AttrConfig when
possible.

See the [Value inheritance](README.md#user-content-value-inheritance)
section for details on how this field is inherited by [Instances](/api/types/Instance).

## globalDesc

 `rbxmk.globalDesc: Desc?`

The **globalDesc** field gets or sets the global root descriptor. Most
items that utilize a root descriptor will fallback to the global descriptor when
possible.

See the [Value inheritance](README.md#user-content-value-inheritance)
section for details on how this field is inherited by [Instances](/api/types/Instance).

# Functions

----

## decodeFormat

 `rbxmk.decodeFormat(format: string, bytes: BinaryString): (value: any)`

The **decodeFormat** function decodes *bytes* into a value according
to *format*. The exact details of each format are described in the [Formats](/api/formats) documents.

decodeFormat will throw an error if the format does not exist, or the format
has no decoder defined.

## encodeFormat

 `rbxmk.encodeFormat(format: string, value: any): (bytes: BinaryString)`

The **encodeFormat** function encodes *value* into a sequence of
bytes according to *format*. The exact details of each format are described
in the [Formats](/api/formats) document.

encodeFormat will throw an error if the format does not exist, or the format
has no encoder defined.

## formatCanDecode

 `rbxmk.formatCanDecode(format: string, type: string): bool`

The **formatCanDecode** function returns whether *format* decodes
into *type*.

formatCanDecode will throw an error if the format does not exist, or the
format does not define types it decodes into.

## get

 `rbxmk.get(instance: Instance, property: string, fallback: string | Desc | nil): (value: any)`

The **get** function gets the *property* of *instance*. If
*instance* has a descriptor, then it is used to determine the type when
getting the property. Otherwise *fallback* is used. If *fallback* is a
string, then the type named by the string is used. If *fallback* is a Desc,
then that descriptor is used. If *fallback* is nil, then the type will be
derived directly from the value of the property.

Note that *fallback* is always treated as less specific than the
descriptor of *instance*. The purpose of the get function is to provide a
descriptor-agnostic way to get properties that have ambiguous types in the
absence of a descriptor. With a descriptor, the function behaves the same as
indexing the property directly. Without a descriptor, the *fallback*
argument is used to determine the type instead.

## loadFile

 `rbxmk.loadFile(path: string): (func: function)`

The **loadFile** function loads the content of a file as a Lua function.
*path* is the path to the file.

The function runs in the context of the calling script.

## loadString

 `rbxmk.loadString(source: string): (func: function)`

The **loadString** function loads the a string as a Lua function.
*source* is the string to load.

The function runs in the context of the calling script.

## propType

 `rbxmk.propType(instance: Instance, property: string): (type: string?)`

The **propType** function returns the unreflected type of the value of
*property* from *instance*. Returns nil if the property is
uninitialized.

## runFile

 `rbxmk.runFile(path: string, ...: any): (...: any)`

The **runFile** function runs the content of a file as a Lua script.
*path* is the path to the file. *args* are passed into the script as
arguments. Returns the values returned by the script.

The script runs in the context of the referred file. Files cannot be run
recursively; if a file is already running as a script, then runFile will throw
an error.

## runString

 `rbxmk.runString(source: string, ...: any): (...: any)`

The **runString** function runs a string as a Lua script. *source* is
the string to run. *args* are passed into the script as arguments. Returns
the values returned by the script.

The script runs in the context of the calling script.

## set

 `rbxmk.set(instance: Instance, property: string, value: any, fallback: string | Desc | nil)`

The **set** function sets the *property* of *instance* to
*value*. If *instance* has a descriptor, then it is used to determine
the type when setting the property. Otherwise, *fallback* is used. If
*fallback* is a string, then the type named by the string is used. If
*fallback* is a Desc, then that descriptor is used. If *fallback* is
nil, then the type will be derived directly from *value*.

Note that *fallback* is always treated as less specific than the
descriptor of instance. The purpose of the set function is to provide a
descriptor-agnostic way to set properties that have ambiguous types in the
absence of a descriptor. With a descriptor, the function behaves the same as
assigning to the property directly. Without a descriptor, the *fallback*
argument is used to determine the type instead.

# Structs

----

## Enum

The **Enum** field is a collection of Enum values defined by rbxmk.

{{<goto page="Enum">}}Enum{{</goto>}}