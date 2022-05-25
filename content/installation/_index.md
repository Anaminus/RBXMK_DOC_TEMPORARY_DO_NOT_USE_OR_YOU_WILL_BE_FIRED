+++
weight = 10
title = "Installation"
description = "How to download and install rbxmk."
titleIcon = "fas fa-download"
+++

# Instructions
The current version of rbxmk is **<version>v0.9.1</version>**.

Select the tab corresponding to your operating system:

{{<snippet>}}
{{<tab title="Windows" type="md">}}
{{<noimpl>}}

*These are instructions for installing rbxmk on [Windows][windows].*

To install rbxmk:
1. Download the [Windows installer](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-windows-setup.zip).
2. Open the installer and follow the prompts.

After installing, any open command prompts will need to be reopened so that they
reflect changes to the environment made by the installer.

Next, verify that rbxmk is installed:
1. Click the **Start menu**.
2. In the menu's search box, type `cmd`, then press the **Enter** key.
3. In the Command Prompt windows that appears, type the following command:

```
rbxmk version
```

4. Confirm that the command prints the installed version of rbxmk.

[windows]: https://microsoft.com/windows

{{</tab>}}
{{<tab title="Mac" type="md">}}
{{<noimpl reason="\"portable\" qualifier">}}
{{<noimpl reason="ARM architecture">}}

*These are instructions for installing rbxmk on [macOS][macos].*

Select the download that corresponds to your operating system's architecture:
- [64-bit](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-darwin-amd64-portable.zip)
- [ARM](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-darwin-arm64-portable.zip)

The executable is contained in a zip archive. After extracting, the executable
should be placed in a location that is in the system [PATH][PATH].

Next, verify that rbxmk is installed:
1. Click the **Launchpad** icon in the Dock.
2. Type `Terminal` in the search field, then click Terminal.
	- Alternatively, the Terminal can be found in the `/Applications/Utilities`
	  folder.
3. In the Terminal window that appears, type the following command:

```
rbxmk version
```

4. Confirm that the command prints the installed version of rbxmk.

[macos]: https://www.apple.com/macos
[PATH]: https://en.wikipedia.org/wiki/PATH_(variable)

{{</tab>}}
{{<tab title="Linux" type="md">}}
{{<noimpl reason="\"portable\" qualifier">}}

*These are instructions for installing rbxmk on [Linux][linux].*

Select the download that corresponds to your operating system's architecture:
- [64-bit](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-amd64-portable.zip)
- [32-bit](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-386-portable.zip)

The executable is contained in a zip archive. After extracting, the executable
should be placed in a location that is in the system [PATH][PATH].

Next, verify that rbxmk is installed:
1. Open a terminal, and type the following command:

```
rbxmk version
```

2. Confirm that the command prints the installed version of rbxmk.

[linux]: https://www.kernel.org/
[PATH]: https://en.wikipedia.org/wiki/PATH_(variable)

{{</tab>}}
{{<tab title="Linux Debian" type="md">}}
{{<noimpl>}}

*These are instructions for installing rbxmk on Linux for [Debian][debian]-based
distributions.*

Select the download that corresponds to your operating system's architecture:
- [64-bit](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-amd64.deb)
- [32-bit](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-386.deb)

If your distribution supports installing `.deb` files directly, use that to
install the downloaded file. Otherwise, `dpkg` can be used. For example, from a
terminal:

```bash
dpkg --install ~/Downloads/rbxmk-v0.9.1-linux-amd64.deb
```

This will install rbxmk, or upgrade if a previous version was installed.

Next, verify that rbxmk is installed:
1. Open a terminal, and type the following command:

```
rbxmk version
```

2. Confirm that the command prints the installed version of rbxmk.

[debian]: https://www.debian.org/
[PATH]: https://en.wikipedia.org/wiki/PATH_(variable)

{{</tab>}}
{{<tab title="Linux RPM" type="md">}}
{{<noimpl>}}

*These are instructions for installing rbxmk on Linux through the [RPM Package
manager][rpm].*

Select the download that corresponds to your operating system's architecture:
- [64-bit](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-amd64.rpm)
- [32-bit](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-386.rpm)

If your distribution supports installing `.rpm` files directly, use that to
install the downloaded file. Otherwise, `rpm` can be used. For example, from a
terminal:

```bash
rpm --upgrade ~/Downloads/rbxmk-v0.9.1-linux-amd64.rpm
```

This will install rbxmk, or upgrade if a previous version was installed.

Next, verify that rbxmk is installed:
1. Open a terminal, and type the following command:

```
rbxmk version
```

2. Confirm that the command prints the installed version of rbxmk.

[rpm]: https://rpm.org/
[PATH]: https://en.wikipedia.org/wiki/PATH_(variable)

{{</tab>}}
{{</snippet>}}

{{<alert type="warning">}}

rbxmk is fully featured, but thorough testing of all features is still a work
in progress. Please practice redundancy and use backups to reduce the risk of
data loss. Be sure to [report][issues] issues as you encounter them!

[issues]: https://github.com/Anaminus/rbxmk/issues

{{</alert>}}

# All downloads
{{<noimpl reason="">}}
<div class="flexzone">
<div>

## Windows
- [Installer](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-windows-setup.zip)
- [Portable (64-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-windows-amd64-portable.zip)
- [Portable (32-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-windows-386-portable.zip)

</div>
<div>

## macOS
- [Portable](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-darwin-amd64-portable.zip)
- [Portable (M1)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-darwin-arm64-portable.zip)

</div>
<div>

## Linux
- [Portable (64-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-amd64-portable.zip)
- [Portable (32-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-386.rpm)
- [Debian package (64-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-amd64.deb)
- [Debian package (32-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-386.deb)
- [RPM package (64-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-amd64.rpm)
- [RPM package (32-bit)](https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/rbxmk-v0.9.1-linux-386-portable.zip)

</div>
</div>

{{<noimpl>}}
*[List of checksums][checksums]*

rbxmk may also be compiled from source. See the [Compiling from
source](installation/compiling) page for more information.

[checksums]: https://github.com/Anaminus/rbxmk/releases/download/v0.9.1/checksums.txt
[source]: https://github.com/Anaminus/rbxmk/archive/v0.9.1.zip
[release]: https://github.com/Anaminus/rbxmk/releases/tag/v0.9.1

<!--

# Install
{{<alert type="warning">}}

Currently, only "portable" builds of rbxmk are available. However, work is being
done to produce installers that will automate the installation process. Stay
tuned!

{{</alert>}}

The executable is contained in a ZIP archive. After extracting, the executable
should be placed in a location that is in the system [PATH][PATH].

[PATH]: https://en.wikipedia.org/wiki/PATH_(variable)

-->
