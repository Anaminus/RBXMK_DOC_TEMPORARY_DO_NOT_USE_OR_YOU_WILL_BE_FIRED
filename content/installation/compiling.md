+++
title = "Compiling from source"
description = "Compiling rbxmk from source."
+++

This document contains information for compiling and installing rbxmk.

{{<alert type="info">}}

rbxmk is written in [Go](https://go.dev/). For development, it is recommend to
be familiar with the [`go` command](https://pkg.go.dev/cmd/go).

{{</alert>}}

# Basic installation
Instead of using prebuilt releases, rbxmk can be installed manually.

1. [Install Go](https://golang.org/doc/install)
2. [Install Git](http://git-scm.com/downloads)
3. Using a shell with Git (such as Git Bash), run the following command:

```bash
go install github.com/anaminus/rbxmk/rbxmk@latest
```

If you installed Go correctly, this will install the latest version of rbxmk to
`$GOPATH/bin`, which will allow you run it directly from a shell. No further
configuration is necessary.

A specific version of rbxmk may be installed by replacing `latest` with a
version number (e.g. `v0.8.0`).

# Building the repository
To compile and install the bleeding-edge version, the best way is to clone the
repository:

```bash
git clone https://github.com/anaminus/rbxmk
cd rbxmk/rbxmk
go install
```

By default, this will install rbxmk with the version set as "imperative".

# Build tags
Several build tags are available to configure how rbxmk is compiled. Tags
can be configured with the `-tags` flag:

```bash
go install -tags "tag1 tag2 etc"
```

The following tags are available:

## `release`
To aid with debugging, the program version is built as "imperative" by default,
indicating the default branch.

```bash
go install
rbxmk version
# imperative
```

To build a release version, the `release` tag must be included:

```bash
go install -tags "release"
rbxmk version
# 0.5.1
```

## `interactive_commands`
Including the `interactive_commands` tag will enable **interactive command
mode**. For windows builds, if the executable is run from Windows Explorer,
rbxmk runs in a mode that allows commands to be used interactively. If not
included, a message is displayed instead.

This feature is locked behind a tag because Cobra commands are currently not
designed to be run more than once. Progress on this issue can be tracked at
[github.com/spf13/cobra#1419][1419].

[1419]: https://github.com/spf13/cobra/issues/1419

## `no_desc_test`
Testing of the `--desc-latest` flag involves downloading an external file, which
can slow down testing. This can be disabled by including the `no_desc_test` tag.

```bash
go test -tags "no_desc_test"
```

## `sslkeylog`
Including the `sslkeylog` tag will compile rbxmk with SSL key logging support.
This is useful for interfacing with external programs like
[Wireshark](https://www.wireshark.org/) to debug HTTPS connections.

Additionally, the linker must be configured to set the
`main.sslKeyLogFileEnvVar` variable to the name of an environment variable. This
environment variable will be used to get the location of a key logging file when
it is available.

For example, Wireshark reads from the file pointed to by the `SSLKEYLOGFILE`
environment variable. To interface with Wireshark, rbxmk can be compiled as
follows:

```bash
go install -tags "sslkeylog" -ldflags="-X main.sslKeyLogFileEnvVar=SSLKEYLOGFILE"
```

Then, when `SSLKEYLOGFILE` is set to, say, `/tmp/sslkeys.log`, rbxmk will write
keys to this file as it makes network requests. Meanwhile, Wireshark will read
keys from this file, and use them to decrypt the network traffic made by rbxmk.

{{<alert type="warning">}}

If the `SSLKEYLOGFILE` environment variable is defined globally, other programs
may respect it inadvertently. Make sure to have it enabled only when debugging.
Or, compile rbxmk with a different variable name.

{{</alert>}}

Because key logging can be a security risk, the `sslkeylog` tag is forced
disabled when the `release` build tag is included.

## Language tags
Support for compilation with alternate languages is available.

By default, the "en-us" language is compiled. To compile with a different
language, the `lang_no_default` tag must be included disable the default
language, then a `lang_*` tag is included to set the desired language.

```bash
go install -tags "lang_no_default lang_en_us"
```

Language build tags are formatted by converting non-letter characters to
underscores, and prefixing with "lang_". For example, `en-us` becomes
`lang_en_us`.

The following language tags are available:

- `lang_en_us`

# Version configuration
Extra version information can be included by passing the `-X` flag to the
linker:

```bash
go install -ldflags="-X $VARIABLE=$VALUE"
```

- The `main.Prerelease` variable appends a prerelease version.
- The `main.Build` variable appends build metadata.

The following example sets the prelease as "rc.1", and sets the build
information to include the current date and commit hash.

```bash
go install -ldflags="-X main.Prerelease=rc.1 -X main.Build=$(echo $(git log -1 --format=%cI | date --utc +%Y%m%d)-$(git rev-parse --short HEAD))"
rbxmk version
# imperative-rc.1+20210312-2070bf8
```

# Cross-compilation
rbxmk can be cross-compiled by setting the `GOOS` and `GOARCH` environment
variables to the target system before compiling. For example, in Bash:

```bash
GOOS=windows GOARCH=amd64 go install -tags "lang_no_default lang_en_us"
```

The page on [Go environment variables][goenvvar] contains more information,
including a list of valid combinations of `GOOS` and `GOARCH`.

[goenvvar]: https://go.dev/doc/install/source#environment
