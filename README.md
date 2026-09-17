# what does saif even do.exe

**Decieve Clone 67.0** is a standalone Windows desktop companion for VALORANT. It keeps the familiar dashboard inside a native app window and bundles the local backend, so users do not need Python, a browser tab, or a separate installer.

[Download the latest Windows EXE](https://github.com/yksaionara/Valorant-Tracker/releases/download/auto-update/what%20does%20saif%20even%20do.exe)

## Automatic updates

The app checks this repository's fixed `auto-update` release whenever it starts. When a newer build is available, it:

1. downloads the replacement EXE;
2. verifies the published file size and SHA-256 checksum;
3. verifies that the download is a Windows PE executable;
4. replaces the current copy and relaunches it.

If GitHub is unavailable, the current version opens normally and checks again next time. Every user must install this updater-enabled release once; future builds update automatically on relaunch. Set `VRC_DISABLE_AUTO_UPDATE=1` before launch to opt out.

## Features

- Native Windows desktop window with the bundled v2.1.0 dashboard design.
- Live match scoreboard with ranks, RR, peak rank, K/D, headshot rate, win rate, account level, party detection, team averages, smurf indicators, and win probability.
- Detailed player profiles, recent form, match history, weapon skins, buddies, sprays, cards, titles, and encounter history.
- Agent-select utilities including map presets, instalock, side checking, and dodge controls.
- Daily Store, Night Market, currency balances, collection value, rank/RR history, and game-setting presets.
- Social information, overlay chat, Discord Rich Presence, and appear-offline controls.
- Offline status commands through the pinned **Decieve Clone 67.0 is active** conversation.
- VALORANT text art opens [valoranttextart.com/browse](https://valoranttextart.com/browse/).

## Changes from Valorant Scout 2.1.0

- Packaged as the single Windows executable `what does saif even do.exe`.
- Replaced browser launching with an embedded native WebView2 window.
- Removed phone/Ably remote mode and its backend dependency.
- Removed the built-in crosshair page.
- Replaced the original branding, application icon, dashboard logo, and offline-status copy.
- Bundled a pinned local dashboard snapshot so upstream site updates and notifications cannot change this build.
- Disabled the upstream sync/telemetry worker in the desktop distribution.
- Added the verified restart-time updater described above.

The full modification record is available in `MODIFICATIONS.md` after reconstructing the source.

## Requirements

- Windows 10 or Windows 11, 64-bit
- Microsoft Edge WebView2 Runtime (included with current Windows installations)
- Riot Client and VALORANT running for live data
- Discord desktop app only if Discord Rich Presence is wanted

## Installation

1. Download **`what does saif even do.exe`** from the release link above.
2. Place it in a folder where your Windows account can write files.
3. Run it. Windows SmartScreen may show an **Unknown publisher** warning because the build is not code-signed.
4. Start VALORANT for live match data. With VALORANT closed, the app can display demo data.

Do not rename or move the EXE while an update is being installed.

## Security and privacy

- Live data is read from the local Riot/VALORANT client APIs.
- The bundled dashboard is served only through the app's loopback server.
- Updates are restricted to this repository's fixed release channel and checked before installation.
- The executable is produced by the public GitHub Actions workflow in this repository.
- Release checksums are published in `manifest.json` beside the EXE.

The build is unsigned. A checksum verifies download integrity; it is not a substitute for a commercial code-signing certificate or an antivirus scan.

## Source and reproducible build

This repository stores the complete modification patch and build workflow. GitHub Actions checks out the exact upstream Valorant Scout v2.1.0 commit, applies the patch, validates the removal of remote mode, compiles the Python sources, builds the Windows executable with PyInstaller, verifies the PE metadata, and publishes the EXE plus its update manifest.

The base source is [kryotrades/Valorant-Scout](https://github.com/kryotrades/Valorant-Scout) at commit `ab466b7da5c44412567baa5b82a5c9d890b71a10`.

## Disclaimer

This is an unofficial community modification. It is not affiliated with, endorsed by, or sponsored by Riot Games. Features that automate client actions may violate Riot Games' rules or result in ordinary dodge penalties; use them at your own risk.

## License and attribution

This modified distribution remains licensed under the [GNU General Public License v3.0](https://github.com/kryotrades/Valorant-Scout/blob/ab466b7da5c44412567baa5b82a5c9d890b71a10/LICENSE). Original Valorant Scout copyright and third-party notices remain with their respective authors. The modification patch and build instructions are published here so recipients can reconstruct the corresponding source for this release.
