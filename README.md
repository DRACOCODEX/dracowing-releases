# DRACOWING

[![latest release](https://img.shields.io/github/v/release/DRACOCODEX/dracowing-releases?label=stable&color=2a6)](https://github.com/DRACOCODEX/dracowing-releases/releases/latest)
[![latest pre-release](https://img.shields.io/github/v/release/DRACOCODEX/dracowing-releases?include_prereleases&label=pre-release&color=d80)](https://github.com/DRACOCODEX/dracowing-releases/releases)

**DRACOWING is an autonomous software team you station on your own machines.** It creates and
manages a **Wing**: a team of one or many **TALONs**, each an autonomous coding instance with its
own model, role and context. You point them at a repository, and DRACOWING verifies every piece of
work they claim to have done before accepting it. The desktop app is Mission Control for that team.

This repository holds **release builds only**. The source is private.

## Download

Go to the **[latest release](https://github.com/DRACOCODEX/dracowing-releases/releases/latest)**
and pick the file for your machine:

| Your machine | Download |
|---|---|
| Mac with Apple Silicon (M1, M2, M3, M4) | `DRACOWING-<version>-mac-arm64.dmg` |
| Mac with Intel | `DRACOWING-<version>-mac-x64.dmg` |
| Windows (most PCs) | `DRACOWING-<version>-win-x64.exe` |
| Windows on ARM (Snapdragon, Surface Pro X) | `DRACOWING-<version>-win-arm64.exe` |
| Linux x86_64, any distribution | `DRACOWING-<version>-linux-x86_64.AppImage` |
| Linux x86_64, Debian / Ubuntu | `DRACOWING-<version>-linux-amd64.deb` |
| Linux ARM64 | `DRACOWING-<version>-linux-arm64.AppImage` or `.deb` |

Not sure which Mac you have? Apple menu → **About This Mac**: "Chip: Apple M…" means Apple
Silicon, "Processor: Intel" means Intel. Each Mac build also comes as a `.zip`, for anyone who
prefers it to a disk image.

## Before you install: Docker

**DRACOWING needs Docker.** The app is the front door: on first launch it checks for Docker,
pulls the DRACOWING server containers (each pinned by digest), and starts them on your machine.

- **macOS / Windows:** install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
  and start it.
- **Linux:** install Docker Engine and the compose plugin.

The first-launch screen tells you exactly which check failed if Docker is missing or not running.

## Install

**macOS:** open the `.dmg` and drag DRACOWING into Applications. The app is not notarized yet, so
the first time, **right-click it → Open → Open**. After that it opens normally.

**Windows:** run the `.exe` installer. It is not code-signed yet, so SmartScreen may say "Windows
protected your PC". Click **More info → Run anyway**. You only see this once.

**Linux, AppImage:**

```bash
chmod +x DRACOWING-*-linux-x86_64.AppImage
./DRACOWING-*-linux-x86_64.AppImage
```

**Linux, deb:**

```bash
sudo apt install ./DRACOWING-*-linux-amd64.deb
```

## Stable and pre-release

Releases here come in two kinds.

| | Stable | Pre-release |
|---|---|---|
| Marked | normal release | **Pre-release** badge |
| Tag looks like | `v0.6.0` | `v0.6.0-rc.1` |
| [`/releases/latest`](https://github.com/DRACOCODEX/dracowing-releases/releases/latest) resolves to | ✅ this | skipped |
| Who it is for | everyone | trying something new early |

**Stable is the default.** The "latest release" link above always points at the newest stable
release, because GitHub skips pre-releases when resolving it. So you never get a pre-release by
accident.

A **pre-release** is newer than stable and less proven. It exists so a change can be tried before
it goes to everyone. To run one, pick it from
[all releases](https://github.com/DRACOCODEX/dracowing-releases/releases).

## Verifying a download

Each release carries a `SHA256SUMS.txt`. From the folder you downloaded into:

```bash
sha256sum -c SHA256SUMS.txt --ignore-missing      # macOS: shasum -a 256 -c SHA256SUMS.txt --ignore-missing
```

`--ignore-missing` skips the files you did not download. Windows (PowerShell):

```powershell
Get-FileHash .\DRACOWING-<version>-win-x64.exe -Algorithm SHA256
```

Then compare the result with the matching line in `SHA256SUMS.txt`.

The builds are not code-signed or notarized yet. Until they are, the checksum is the thing to
check.

## What each release contains

Ten installers covering six platforms (macOS, Windows and Linux, each on x86_64 and arm64), plus
`SHA256SUMS.txt`:

- macOS: `.dmg` and `.zip` for arm64 and x64
- Windows: `.exe` installer for x64 and arm64
- Linux: `.AppImage` and `.deb` for x86_64 and arm64

## Links

- [Latest stable release](https://github.com/DRACOCODEX/dracowing-releases/releases/latest)
- [All releases, including pre-releases](https://github.com/DRACOCODEX/dracowing-releases/releases)

Issues and questions go to the DRACOFORCE team.
