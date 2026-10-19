# noctalia-qs

> [!NOTE]
> This is a **community-maintained fork** of the archived [noctalia-dev/noctalia-qs](https://github.com/noctalia-dev/noctalia-qs). It exists to keep [Noctalia Shell v4](https://github.com/DBeidachazi/noctalia-shell) (AUR: `noctalia-legacy-v4`) building and running on current Arch Linux.
> AUR package: [`noctalia-qs-legacy-v4`](https://aur.archlinux.org/packages/noctalia-qs-legacy-v4), built from [`packaging/aur/PKGBUILD`](packaging/aur/PKGBUILD). It `provides` and `conflicts` with the original `noctalia-qs` so that you can decide knowingly whether to switch to this fork.
>
> Changes since upstream v0.0.12:
> - **Qt 6.12 build fix**: ported upstream Quickshell's "use MOC includes instead of opaque pointer definitions" so Hyprland/i3 IPC and PipeWire compile again (`Meta Types must be fully defined`).
> - Includes the fixes upstream merged after v0.0.12 but never released: PipeWire use-after-free and device-disconnect crash fixes, Bluetooth rfkill unblock, ObjectModel reorder fix.
>
> Please report problems with this fork here, not to the upstream Noctalia or Quickshell projects.

**noctalia-qs** is a custom fork of [Quickshell](https://quickshell.org) — a flexible QtQuick-based desktop shell toolkit for Wayland. It serves as the shell framework powering [Noctalia Shell](https://github.com/DBeidachazi/noctalia-shell).

## What is noctalia-qs?

noctalia-qs extends Quickshell with features and patches specific to the Noctalia shell ecosystem, including:

- `ext-background-effect-v1` Wayland protocol support
- Noctalia-specific build defaults and configuration

The binary is named `qs` and is a drop-in replacement for `quickshell` when using Noctalia Shell.

## Credits

noctalia-qs is built on top of **Quickshell**, developed by [outfoxxed](https://git.outfoxxed.me/outfoxxed) and contributors.

- Quickshell website: https://quickshell.org
- Quickshell source: https://git.outfoxxed.me/quickshell/quickshell
- Quickshell mirror: https://github.com/quickshell-mirror/quickshell

All credit for the core framework goes to the Quickshell project and its contributors.

## Building

See [BUILD.md](BUILD.md) for build instructions.

```bash
cmake -GNinja -B build -DCMAKE_BUILD_TYPE=RelWithDebInfo -DCMAKE_INSTALL_PREFIX=/usr/local
cmake --build build
sudo cmake --install build
# binary: build/src/quickshell
```

Or use the provided script for a clean build + install:

```bash
./bin/build.sh
```

## License

Licensed under the GNU LGPL 3, same as the upstream Quickshell project.

Unless you explicitly state otherwise, any contribution submitted for inclusion shall be licensed as above, without any additional terms or conditions.
