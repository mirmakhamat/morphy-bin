# Morphy for Arch Linux

Unofficial Arch Linux packaging for [Morphy](https://appmorphy.com/), an infinite canvas for working with AI agents.

This repository provides a PKGBUILD for installing the official Morphy Linux binary package on Arch Linux.

> **Disclaimer:** This is an unofficial community project. It is not affiliated with or endorsed by the Morphy developers.

## Features

- Install Morphy using `makepkg`
- Add a desktop application entry and application icon
- Launch Morphy from the application menu or using the `morphy` command
- Package the upstream binary without modifying the application itself

## Requirements

- Arch Linux or a compatible distribution
- `base-devel`
- `git`
- Runtime dependencies listed in `PKGBUILD`

Install the build tools:

```bash
sudo pacman -S --needed base-devel git
```

## Installation

Clone the repository:

```bash
git clone https://github.com/mirmakhamat/morphy-bin.git
cd morphy-bin
```

Build and install:

```bash
makepkg -si
```

Launch Morphy:

```bash
morphy
```

You can also launch it from your desktop application menu.

## Updating

When a new upstream release becomes available, update `pkgver`, verify the source URL, and calculate the SHA-256 checksum of the new package.

Then rebuild and install:

```bash
makepkg -si
```

## Troubleshooting

### Blurry interface on Wayland

Try launching Morphy with the Wayland backend:

```bash
morphy --ozone-platform=wayland
```

Alternatively, try XWayland with a device scale factor:

```bash
morphy --ozone-platform=x11 --force-device-scale-factor=1.5
```

The result depends on your display scaling and desktop configuration.

## License

The packaging files and original documentation in this repository are licensed under the MIT License.

The MIT License does not apply to the Morphy application, its binaries, trademarks, or other upstream assets. Those remain subject to their respective owners' terms.

See the upstream [Morphy website](https://appmorphy.com/) for information about the application.
