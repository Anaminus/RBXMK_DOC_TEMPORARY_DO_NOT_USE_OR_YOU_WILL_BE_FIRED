+++
weight = 1
title = "doc"
description = "Display API documentation."
categories = ["Command"]
+++

`rbxmk doc 	REFERENCE
`

The **doc** command displays documentation for a given API or topic.

Topics are stored in a tree, where each topic may have sub-topics. A
"reference", similar to a file path, can refer to a topic, or a section within a
topic. The presence of a `:` separator causes the *reference* to
begin drilling into the sections of the topic to the left of the separator. The
topic portion of a reference is case-insensitive, while the section portion is
case-sensitive.

For example,

```
rbxmk doc types/Instance:Methods/FindFirstChild
```

This reference will start at the top-level "types" topic, then drill into the
"Instance" sub-topic, then drill into the "Method" section, then the
"FindFirstChild" sub-section. The doc command will then display the content of
this sub-section only.

If the referred topic has no content, but has sub-topics, then these
sub-topics are listed instead (see `--list`). If no reference is
specified, then all top-level topics are listed.

The following top-level topics are available:

- commands
- example
- flags
- formats
- interactive
- libraries
- messages
- types
- usage

# Flags

----

## export

`--export` `(default: "false")`

Ensure that content is formatted for output, rather than for display in the
terminal. Applies to the "terminal" format.

## format

`-f, --format string` `(default: "terminal")`

Sets the output format of the produced fragment. Available formats are
"terminal", "html".

## list

`-l, --list` `(default: "false")`

Returns a list of sub-topics and sub-sections for the given reference. If no
reference is specified, then all top-level topics are listed.

Each item in the list is a reference relative to the given reference. The
top-level sections of a topic will be prefixed with ":". Sub-topics and
sub-sections of sections will be prefixed with "/". In effect, the whole name of
a listed item, including the prefix, can be appended to the current reference to
query that item.

## recursive

`-r, --recursive` `(default: "false")`

List references recursively. Implies --list.

## width

`-w, --width int` `(default: "0")`

When possible, render formatted fragments with the given width, wrapping text
around. If 0, then no wrapping is applied. If less than 0, then the width is
based on the current context (for example, the "terminal" format renders with
the current width of the terminal).