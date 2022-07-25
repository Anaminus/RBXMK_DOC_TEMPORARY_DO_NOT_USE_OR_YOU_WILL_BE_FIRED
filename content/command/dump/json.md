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
| Libraries | array | A list of libraries available in the Lua environment. Each element is a Library object. |
| Types | object? | A collection of globally defined data types. Maps a type name to a TypeDef object. |
| Enums | object? | A collection of globally defined enums. Maps an enum name to an Enum object. |
| Formats | object | A collection of globally defined formats. Maps a type name to a Format object. |
| Program | object | A Command object describing the top-level program command. |
| Fragments | array | A list of additional fragment references. Each element is a string. |
| Description | string? | A fragment reference to a description of the Lua API overall. |

## Library

A **Library** is an object that describes a library. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Name | string | The name of the library. |
| ImportedAs | string | The name the library is imported under. If empty, then the library is merged into the global environment. |
| Priority | int | The priority that determines the order in which the library is loaded. Libraries are loaded by ascending priority. |
| Struct | object? | A Struct object that describes the contents of the library. |
| Types | object? | A collection of data types defined by the library. Maps a type name to a TypeDef object. |
| Enums | object? | A collection of enums defined by the library. Maps an enum name to an Enum object. |

## Format

A **Format** is an object that describes a format. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Summary | string? | A fragment reference to a short summary of the format. |
| Description | string? | A fragment reference to a detailed description of the format. |

## Struct

A **Struct** is an object that describes a table-like value that has a
number of constant fields. It has the following fields.

| Field | Type | Description |
| --- | --- | --- |
| Fields | object | The fields of the structure. Maps a field name to a Field object. |
| Summary | string? | A fragment reference to a short summary of the structure. |
| Description | string? | A fragment reference to a detailed description of the structure. |

## Field

A **Field** is an object that describes the field of a Struct. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Kind | string | Determines the type of the Value field. |
| Value | ... | Describes the field. |

The following values are possible for the Kind field:

| Kind | Value type | Description |
| --- | --- | --- |
| Function | object | Describes a function. Value is a Function object. |
| MultiFunction | array | Describes a function with multiple signatures. Each element is a Function object. |
| Property | object | Describes a property. Value is a Property object. |
| Struct | object | Describes a struct. Value is a Struct object. |

## Property

| Field | Type | Description |
| --- | --- | --- |
| ValueType | object | A Type object that describes the value type of the property. |
| ReadOnly | bool? | Whether the property can be written. |
| Summary | string? | A fragment reference to a short summary of the property. |
| Description | string? | A fragment reference to a detailed description of the property. |

## Function

A **Function** is an object that describes a function. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Parameters | array | Describes the values received by the function. Each element is a Parameter object. |
| Returns | array | Describes the values returned by the function. Each element is a Parameter object. |
| CanError | bool? | Whether the function may throw an error, excluding type errors from received arguments. |
| Summary | string? | A fragment reference to a short summary of the function. |
| Description | string? | A fragment reference to a detailed description of the function. |

## TypeDef

A **TypeDef** object describes the definition of a type. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Category | string? | Describes the category of the type. |
| Underlying | object? | A Type object that describes the underlying type, if any. |
| Operators | object? | An Operators object that describes the operators defined on the type. |
| Properties | object? | Describes the properties defined on the type. Maps a property name to a Property object. |
| Symbols | object? | Describes the symbols defined on the type. Maps a symbol name to a Property object. |
| Methods | object? | Describes the methods defined on the type. Maps a method name to a Function object. |
| Constructors | object? | Describes constructor functions that create the type. Maps a constructor name to an array of Function objects. |
| Enums | object? | Describes enums related to the type. Maps an enum name to an Enum object. |
| Summary | string | A fragment reference pointing to a short summary of the type. |
| Description | string | A fragment reference pointing to a detailed description of the type. |

## Enum

An **Enum** object describes an enum. It has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| Items | object | Describes the items of the enum. Maps an item name to an EnumItem object. |
| Summary | string | A fragment reference pointing to a short summary of the enum. |
| Description | string | A fragment reference pointing to a detailed description of the enum. |

## EnumItem

An **EnumItem** object describes an enum item. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Value | number | The value of the item. |
| Summary | string? | A fragment reference pointing to a short summary of the item. |
| Description | string? | A fragment reference pointing to a detailed description of the item. |

## Command

A **Command** object describes a program command. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Summary | string? | A fragment reference pointing to a short summary of the command. |
| Description | string? | A fragment reference pointing to a detailed description of the command. |
| Flags | object? | Describes the flags of the command. Maps a flag name to a Flag object. |
| Commands | object? | Describes the sub-commands of the command. Maps a command name to a Command object. |

## Flag

A **Flag** object describes a flag of a program command. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Type | string | Indicates the value type of the flag. |
| Default | string? | Indicates the default value for the flag. |
| Deprecated | string? | Indicates whether the flag is deprecated, and if so, the new flag to use. |
| Hidden | bool? | Indicates whether the flag is hidden. |
| Shorthand | string? | Indicates a one-letter abbreviation for the flag. |
| ShorthandDeprecated | string? | Indicates whether the shorthand of the flag is deprecated, and if so, the new flag to use. |
| Description | string? | A fragment reference pointing to a description of the flag. |

## Parameter

A **Parameter** object describes the parameter of a function.

| Field | Type | Description |
| --- | --- | --- |
| Name | string? | The name of the parameter. |
| Type | object | A Type object that describes the type of the parameter. |
| Default | string? | The default value if the type is optional. Always omitted for return values. |
| Enums | array? | Literal values that can be passed to the parameter. Each element is a string. |

## Type

A **Type** object describes the type of a value. It has the following
fields.

| Field | Type | Description |
| --- | --- | --- |
| Sig | string | A string-representation of the type, in Luau type definition format. |
| Kind | string | Indicates the remaining fields. |
| ... | ... | Additional fields indicated by the Kind field. |

### primitive

The **primitive** kind describes a primitive value. It has the following
additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Type | string | The name of the type. |

### function

The **function** kind describes the signature of a function. It has the
following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Parameters | array | The values received by the function. Each element is a Parameter object. |
| Returns | array | The values returned by the function. Each element is a Parameter object. |

### array

The **array** kind describes an array of elements, each with a single
type. It has the following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Type | object | A Type object indicating each element of the array. |

### or

The **or** kind describes a union of two or more types. It has the
following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Types | array | An array of Type objects. |

### optional

The **optional** kind describes a type that can also be nil. It has the
following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Type | object | A Type object indicating the underlying type. |

### group

The **group** kind groups the underlying type. It has the following
additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Type | object | A Type object indicating the underlying type. |

### struct

The **struct** kind describes a table with a number of named fields. It
has the following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Fields | object | The fields of the struct. Maps a field name to a Type object. |

### map

The **map** kind describes a table where each element maps a key to a
value. It has the following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Key | object | A Type object indicating the type of each key. |
| Value | object | A Type object indicating the type of each value. |

### dictionary

The **dictionary** kind describes a table where each element maps a string
to a value. It has the following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Value | object | A Type object indicating the type of each value. |

### table

The **table** kind describes a table with both a map part and a struct
part. It has the following additional fields:

| Field | Type | Description |
| --- | --- | --- |
| Key | object | A Type object indicating the type of each key. |
| Value | object | A Type object indicating the type of each value. |
| Fields | object | The fields of the table. Maps a field name to a Type object. |

### functions

The **functions** kind describes a function with multiple signatures. It
has no additional fields.

## Operators

An **Operators** object describes the operators of a type. It has the
following fields:

| Field | Type | Description |
| --- | --- | --- |
| Add | array | An array of Binop objects that describes signatures for the \_\_add operator. |
| Sub | array | An array of Binop objects that describes signatures for the \_\_sub operator. |
| Mul | array | An array of Binop objects that describes signatures for the \_\_mul operator. |
| Div | array | An array of Binop objects that describes signatures for the \_\_div operator. |
| Mod | array | An array of Binop objects that describes signatures for the \_\_mod operator. |
| Pow | array | An array of Binop objects that describes signatures for the \_\_pow operator. |
| Concat | array | An array of Binop objects that describes signatures for the \_\_concat operator. |
| Eq | object? | A Cmpop object that describes the signature for the \_\_eq operator, if defined. |
| Le | object? | A Cmpop object that describes the signature for the \_\_le operator, if defined. |
| Lt | object? | A Cmpop object that describes the signature for the \_\_lt operator, if defined. |
| Len | object? | A Unop object that describes the signature for the \_\_len operator, if defined. |
| Unm | object? | A Unop object that describes the signature for the \_\_unm operator, if defined. |
| Call | object? | A Function object that describes the signature for the \_\_call operator, if defined. |
| Index | object? | A Function object that describes the signature for the \_\_index operator, if defined. |
| Newindex | object? | A Function object that describes the signature for the \_\_newindex operator, if defined. |

## Binop

A **Binop** object describes a binary operator. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Operand | object | The type of the right operand. |
| Result | object | The type of the result of the operation. |
| Summary | string? | A fragment reference pointing to a short summary of the operator. |
| Description | string? | A fragment reference pointing to a detailed description of the operator. |

## Cmpop

A **Cmpop** object describes a comparison operator. It has the following
fields:

| Field | Type | Description |
| --- | --- | --- |
| Summary | string? | A fragment reference pointing to a short summary of the operator. |
| Description | string? | A fragment reference pointing to a detailed description of the operator. |

## Unop

A **Unop** object describes a unary operator.

| Field | Type | Description |
| --- | --- | --- |
| Result | object | The type of the result of the operation. |
| Summary | string? | A fragment reference pointing to a short summary of the operator. |
| Description | string? | A fragment reference pointing to a detailed description of the operator. |