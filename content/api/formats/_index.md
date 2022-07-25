+++
weight = 30
title = "Formats"
description = "Format reference."
+++

The following formats are available:

<div class="column-list">

<!-- REGION:formats -->
- [bin](/api/formats/bin.md)
- [client.lua](/api/formats/client.lua.md)
- [client.luau](/api/formats/client.luau.md)
- [csv](/api/formats/csv.md)
- [desc-patch.json](/api/formats/desc-patch.json.md)
- [desc.json](/api/formats/desc.json.md)
- [json](/api/formats/json.md)
- [l10n.csv](/api/formats/l10n.csv.md)
- [localscript.lua](/api/formats/localscript.lua.md)
- [localscript.luau](/api/formats/localscript.luau.md)
- [lua](/api/formats/lua.md)
- [luau](/api/formats/luau.md)
- [modulescript.lua](/api/formats/modulescript.lua.md)
- [modulescript.luau](/api/formats/modulescript.luau.md)
- [patch.json](/api/formats/patch.json.md)
- [rbxattr](/api/formats/rbxattr.md)
- [rbxl](/api/formats/rbxl.md)
- [rbxlx](/api/formats/rbxlx.md)
- [rbxm](/api/formats/rbxm.md)
- [rbxmx](/api/formats/rbxmx.md)
- [script.lua](/api/formats/script.lua.md)
- [script.luau](/api/formats/script.luau.md)
- [server.lua](/api/formats/server.lua.md)
- [server.luau](/api/formats/server.luau.md)
- [txt](/api/formats/txt.md)
<!-- /REGION:formats -->

</div>

# Details
A **format** is capable of encoding a value to raw bytes, or decoding raw bytes
into a value. A format can be accessed at a low level through the
[rbxmk.encodeFormat](api/libraries/rbxmk#encodeFormat) and
[rbxmk.decodeFormat](api/libraries/rbxmk#decodeFormat) functions.

The name of a format corresponds to the extension of a file name. For example,
the `lua` format corresponds to the `.lua` file extension. When determining a
format from a file extension, format names are greedy; if a file extension is
`.server.lua`, this will select the `server.lua` format before the `lua` format.
For convenience, in places where a format name is received, the name may have an
optional leading `.` character.

APIs that require a format receive a [FormatSelector](api/types/FormatSelector).
A selector is usually a string that specifies the name of the format to use. A
selector can instead be a table, where the "Format" field specifies the name,
and a number of additional options can be configured for the format. The options
available depend on the format.

A format can decode into a number of certain types, and encode a number of
certain types.

Some formats may only encode or only decode.

Defined for this documentation, a format that can encode a **Stringable** type
accepts any type that can be converted to a string. Additionally, an
[Instance](api/types/Instance) will be accepted as a Stringable when it has a
particular [ClassName](api/types/Instance#ClassName), with a selected property
that has a [Stringlike](api/types/Stringlike) value. In this case, the property
is encoded. The following instances are Stringable:

ClassName         | Property
------------------|---------
LocalizationTable | Contents
LocalScript       | Source
ModuleScript      | Source
Script            | Source

A format that can encode a **Numberable** type accepts any type that can be
converted to a floating-point number. An **Intable** is similar, converting to
an integer instead.
