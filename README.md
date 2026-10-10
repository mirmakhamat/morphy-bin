# Morphy for Arch Linux

Unofficial Arch Linux packaging for [Morphy](https://get.appmorphy.com/), an infinite canvas for working with AI agents.

This repository provides a PKGBUILD to install Morphy on Arch Linux and other compatible distributions.

> **Disclaimer:** This is an unofficial community packaging project. It is not affiliated with, endorsed by, or maintained by the official Morphy developers.

## Features

- Install Morphy using `makepkg`
- Add a desktop application entry
- Register the application icon
- Launch Morphy using the `morphy` command
- Keep packaging instructions separate from the upstream application

## Requirements

- Arch Linux or a compatible distribution
- `base-devel`
- `git`
- Dependencies listed in `PKGBUILD`

Install the basic build tools:

```bash
sudo pacman -S --needed base-devel git
```

## Installation

Clone this repository:

```bash
git clone https://github.com/mirmakhamat/morphy-bin.git
cd morphy-bin
```

Build and install the package:

```bash
makepkg -si
```

After installation, launch Morphy with:

```bash
morphy
```

You can also launch it from your desktop application menu.

## Updating

When a new Morphy release becomes available, the package version and source checksum must be updated in `PKGBUILD`.

Then rebuild and install the updated package:

```bash
makepkg -si
```

## Troubleshooting

### Blurry application interface

If the interface looks blurry under Wayland or fractional display scaling, try launching Morphy with a different rendering backend:

```bash
morphy --ozone-platform=wayland
```

Or try XWayland:

```bash
morphy --ozone-platform=x11 --force-device-scale-factor=1.5
```

The best option depends on your desktop environment and display scaling configuration.

## License

The packaging files in this repository, including the PKGBUILD and original documentation, are licensed under the MIT License.

This license does not apply to the Morphy application, its binaries, trademarks, or other upstream assets. These remain subject to their respective owners' terms and licensing conditions.

This is an unofficial community packaging project and is not affiliated with the Morphy developers.
