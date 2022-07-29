+++
weight = 1
title = "json"
description = "General JSON format."
categories = ["Command", "Subcommand"]
+++

`rbxmk dump json`

The **json** dump format describes the API of the Lua environment in JSON
format.

The top-level value is a JSON object. The **Version** field is a number
that signals the structure of the JSON format, and will be present in all
versions of the format.

Run `rbxmk doc "Commands/dump/json:Structure"` for a detailed
description of the structure.

# Flags

----

## help

`-h, --help`

**Default:** `false`

Displays help for the command.

## indent

`--indent string`

**Default:** `"\t"`

Specifies the spacing used to indent the JSON output. If empty, the output will
be minified (use --indent="" to specify an empty string).

# Structure

----

The following top-level fields are specified:

| Fields | Type | Description |
| --- | --- | --- |
| Version | number | Reserved for indicating different versions of the structure. Always 0. |
| Libraries | array | A list of libraries available in the Lua environment. Each element is a [Library](#library) object. |
| Types | object? | A collection of globally defined data types. Maps a type name to a [TypeDef](#typedef) object. |
| Enums | object? | A collection of globally defined enums. Maps an enum name to an [Enum](#enum) object. |
| Formats | object? | A collection of globally defined formats. Maps a type name to a [Format](#format) object. |
| Program | object | A [Command](#command) object describing the top-level program command. |

## Command

A **Command** object describes a program command. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Aliases | array? | An array of strings listing available aliases of the command. |
| Hidden | bool? | Whether the command is hidden. |
| Summary | string? | A fragment reference pointing to a short summary of the command. |
| Description | string? | A fragment reference pointing to a detailed description of the command. |
| Flags | object? | Describes the flags of the command. Maps a flag name to a [Flag](#flag) object. |
| Commands | object? | Describes the sub-commands of the command. Maps a command name to a [Command](#command) object. |

### Flag

A **Flag** object describes a flag of a program command. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Type | string | Indicates the value type of the flag. |
| Default | string? | Indicates the default value for the flag. |
| Shorthand | string? | Indicates a one-letter abbreviation for the flag. |
| Hidden | bool? | Indicates whether the flag is hidden. |
| Persistent | bool? | Indicates whether the flag is inherited by subcommands. |
| Description | string? | A fragment reference pointing to a description of the flag. |
| Deprecated | string? | Indicates whether the flag is deprecated, and if so, the new flag to use. |
| ShorthandDeprecated | string? | Indicates whether the shorthand of the flag is deprecated, and if so, the new flag to use. |

## Enum

An **Enum** object describes an enum. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Summary | string | A fragment reference pointing to a short summary of the enum. |
| Description | string | A fragment reference pointing to a detailed description of the enum. |
| Items | object | Describes the items of the enum. Maps an item name to an [EnumItem](#enumitem) object. |

### EnumItem

An **EnumItem** object describes an enum item. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Value | number | The value of the item. |
| Summary | string? | A fragment reference pointing to a short summary of the item. |
| Description | string? | A fragment reference pointing to a detailed description of the item. |

## Format

A **Format** is an object that describes a format. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Summary | string? | A fragment reference to a short summary of the format. |
| Description | string? | A fragment reference to a detailed description of the format. |
| Options | object? | The options of the format. Maps an option name to a [FormatOption](#formatoption) object. |

### FormatOption

A **FormatOption** is an object that describes an option of a format. It
has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Type | object | A [Type](#type) object that describes the value type of the option. |
| Default | string | A string describing the default value of the option. |
| Description | string? | A fragment reference to a description of the option. |

## Function

A **Function** is an object that describes a function. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| CanError | bool? | Whether the function may throw an error, excluding type errors from received arguments. |
| Summary | string? | A fragment reference to a short summary of the function. |
| Description | string? | A fragment reference to a detailed description of the function. |
| Parameters | array | Describes the values received by the function. Each element is a [Parameter](#parameter) object. |
| Returns | array | Describes the values returned by the function. Each element is a [Parameter](#parameter) object. |

### Parameter

A **Parameter** object describes the parameter of a function.

| Field | Type | Description |
| --- | --- | --- |
| Name | string? | The name of the parameter. |
| Type | object | A [Type](#type) object that describes the type of the parameter. |
| Default | string? | The default value if the type is optional. Always omitted for return values. |
| Enums | array? | Literal values that can be passed to the parameter. Each element is a string. |

## Library

A **Library** is an object that describes a library. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Name | string | The name of the library. |
| ImportedAs | string | The name the library is imported under. If empty, then the library is merged into the global environment. |
| Priority | int | The priority that determines the order in which the library is loaded. Libraries are loaded by ascending priority. |
| Types | object? | A collection of data types defined by the library. Maps a type name to a [TypeDef](#typedef) object. |
| Enums | object? | A collection of enums defined by the library. Maps an enum name to an [Enum](#enum) object. |
| Struct | object? | A [Struct](#struct) object that describes the contents of the library. |

## Operators

An **Operators** object describes the operators of a type. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Add | array | An array of [Binop](#binop) objects that describes signatures for the \_\_add operator. |
| Sub | array | An array of [Binop](#binop) objects that describes signatures for the \_\_sub operator. |
| Mul | array | An array of [Binop](#binop) objects that describes signatures for the \_\_mul operator. |
| Div | array | An array of [Binop](#binop) objects that describes signatures for the \_\_div operator. |
| Mod | array | An array of [Binop](#binop) objects that describes signatures for the \_\_mod operator. |
| Pow | array | An array of [Binop](#binop) objects that describes signatures for the \_\_pow operator. |
| Concat | array | An array of [Binop](#binop) objects that describes signatures for the \_\_concat operator. |
| Eq | object? | A [Cmpop](#cmpop) object that describes the signature for the \_\_eq operator, if defined. |
| Le | object? | A [Cmpop](#cmpop) object that describes the signature for the \_\_le operator, if defined. |
| Lt | object? | A [Cmpop](#cmpop) object that describes the signature for the \_\_lt operator, if defined. |
| Len | object? | A [Unop](#unop) object that describes the signature for the \_\_len operator, if defined. |
| Unm | object? | A [Unop](#unop) object that describes the signature for the \_\_unm operator, if defined. |
| Call | object? | A [Function](#function) object that describes the signature for the \_\_call operator, if defined. |
| Index | object? | A [Function](#function) object that describes the signature for the \_\_index operator, if defined. |
| Newindex | object? | A [Function](#function) object that describes the signature for the \_\_newindex operator, if defined. |

### Binop

A **Binop** object describes a binary operator. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Operand | object | The [Type](#type) of the right operand. |
| Result | object | The [Type](#type) of the result of the operation. |
| Summary | string? | A fragment reference pointing to a short summary of the operator. |
| Description | string? | A fragment reference pointing to a detailed description of the operator. |

### Cmpop

A **Cmpop** object describes a comparison operator. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Summary | string? | A fragment reference pointing to a short summary of the operator. |
| Description | string? | A fragment reference pointing to a detailed description of the operator. |

### Unop

A **Unop** object describes a unary operator.

| Field | Type | Description |
| --- | --- | --- |
| Result | object | The [Type](#type) of the result of the operation. |
| Summary | string? | A fragment reference pointing to a short summary of the operator. |
| Description | string? | A fragment reference pointing to a detailed description of the operator. |

## Property

A **Property** describes a single value within a structure. It has the
following fields.

| Field | Type | Description |
| --- | --- | --- |
| ValueType | object | A [Type](#type) object that describes the value type of the property. |
| ReadOnly | bool? | Whether the property can be written. |
| Summary | string? | A fragment reference to a short summary of the property. |
| Description | string? | A fragment reference to a detailed description of the property. |

## Struct

A **Struct** is an object that describes a table-like value that has a
number of constant fields. It has the following fields.

| Field | Type | Description |
| --- | --- | --- |
| Summary | string? | A fragment reference to a short summary of the structure. |
| Description | string? | A fragment reference to a detailed description of the structure. |
| Fields | object | The fields of the structure. Maps a field name to a [Field](#field) object. |

### Field

A **Field** is an object that describes the field of a [Struct](#struct). A struct field may have one of a number of kinds of
type, so the Field object has exactly one field, where the key indicates the
kind, and the value describes type. The following kinds are possible:

| Kind | Value type | Description |
| --- | --- | --- |
| Enum | object | Describes an enum. Value is an [Enum](#enum) object. |
| Function | object | Describes a function. Value is a [Function](#function) object. |
| MultiFunction | array | Describes a function with multiple signatures. Each element is a [Function](#function) object. |
| Property | object | Describes a property. Value is a [Property](#property) object. |
| Struct | object | Describes a struct. Value is a [Struct](#struct) object. |

## TypeDef

A **TypeDef** object describes the definition of a type. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Category | string? | Describes the category of the type. |
| Underlying | object? | A [Type](#type) object that describes the underlying type, if any. |
| Requires | array? | An array of strings, listing the names of types that the type depends on. |
| Summary | string | A fragment reference pointing to a short summary of the type. |
| Description | string | A fragment reference pointing to a detailed description of the type. |
| Constructors | object? | Describes constructor functions that create the type. Maps a constructor name to an array of [Function](#function) objects. |
| Properties | object? | Describes the properties defined on the type. Maps a property name to a [Property](#property) object. |
| Symbols | object? | Describes the symbols defined on the type. Maps a symbol name to a [Property](#property) object. |
| Methods | object? | Describes the methods defined on the type. Maps a method name to a [Function](#function) object. |
| Operators | object? | An [Operators](#operators) object that describes the operators defined on the type. |
| Enums | object? | Describes enums related to the type. Maps an enum name to an [Enum](#enum) object. |

## Type

A **Type** object describes the type of a value. It has the
`Sig` field, which is a string-representation of the type formatted
as a Luau type definition.

The object has exactly one additional field, where the key indicates the kind
of type, and the value describes the kind. The following fields are
possible:

### array

**Type:** [Type](#type)

The **array** kind indicates an array of elements, each element having the
inner type.

### dictionary

**Type:** [Type](#type)

The **dictionary** kind describes a table where each element maps a string
to a value. The inner type object indicates the type of each value in the
map.

### function

**Type:** object

The **function** kind describes the signature of a function. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Parameters | array? | The values received by the function. Each element is a [Parameter](#parameter) object. If unspecified, the function has no parameters. |
| Returns | array? | The values returned by the function. Each element is a [Parameter](#parameter) object. If unspecified, the function returns no values. |

### functions

**Type:** object

The **functions** kind indicates a function with multiple signatures. It
has no fields.

### group

**Type:** [Type](#type)

The **group** kind groups the inner type.

### map

**Type:** object

The **map** kind describes a table where each element maps a key to a
value. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Key | object | A [Type](#type) object indicating the type of each key. |
| Value | object | A [Type](#type) object indicating the type of each value. |

### optional

**Type:** [Type](#type)

The **optional** kind describes a type that can also be nil.

### or

**Type:** array

The **or** kind describes a union of two or more types. Each element of
the array is a [Type](#type) object.

### primitive

**Type:** string

The **primitive** kind indicates the type of a primitive value.

### struct

**Type:** object

The **struct** kind describes a table with a number of named fields. Each
field maps a name to a [Type](#type) object.

### table

**Type:** object

The **table** kind describes a table with both a map part and a struct
part. It has the following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Key | object | A [Type](#type) object indicating the type of each key. |
| Value | object | A [Type](#type) object indicating the type of each value. |
| Fields | object | The fields of the table. Maps a field name to a [Type](#type) object. |