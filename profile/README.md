# To Recomp

Static recompilation of the **Tales of** series: each game is translated ahead of time into native code that runs on a modern PC, with no emulator in the loop. The goal is to cover the whole main series, console by console, starting from the original releases.

## Where we are

The project is young. The pilot is **Tales of Symphonia** on GameCube (PAL French reference dump, Japan and USA tracked): the recompiled game boots from the user's own disc, renders through an OpenGL backend and is currently **alpha**. Audio, guest threads and memory card saves are the main missing pieces.

Everything else in the catalog (Phantasia to Arise, on PlayStation, PSP, Wii, Xbox, Switch, 3DS and others) is **planned**: no code exists yet for those games.

## Repositories

| Repository | Role | Status |
| --- | --- | --- |
| [tos-recomp](https://github.com/To-Recomp/tos-recomp) | Tales of Symphonia (GameCube), the pilot | alpha |
| [gcrecomp](https://github.com/To-Recomp/gcrecomp) | GameCube recompiler and runtime (PowerPC 750, GX, audio, input, Dolphin OS). Fork of [sp00nznet/gcrecomp](https://github.com/sp00nznet/gcrecomp) | in use by tos-recomp |
| [common](https://github.com/To-Recomp/common) | Shared C++17 library: disc reading (ISO, CISO, GCZ, WIA, RVZ), dump verification, extraction | GameCube only |
| [launcher](https://github.com/To-Recomp/launcher) | Tauri + Svelte app to install, prepare, configure and launch the recomps | scaffold |
| [catalog](https://github.com/To-Recomp/catalog) | `catalog.json`: games and platforms shown in the launcher, edited by pull request | active |
| [tools](https://github.com/To-Recomp/tools) | Recompilation tools we write ourselves (for example a 65816 recompiler for the SNES) | skeleton |

Tools we only fork keep their original name and live in the organization as separate forks.

## What we will cover

- **Games**: the main Tales of games, from *Phantasia* (1995) to *Arise* (2021), one `<game>-recomp` repository per game once work starts.
- **Platforms**: GameCube first, then the other platforms of each game (Super Famicom, PlayStation 1/2/3, PSP, Wii, Xbox 360, 3DS and later releases). Each platform needs its own recompiler or toolchain; shared parts go to `common`.
- **One launcher**: a single place to install, prepare and run every recomp. Each recomp stays usable standalone, and releases also work with RecompLauncher through a `recomplauncher.json` manifest.

## Ground rules

- **No game files.** You bring your own copy of the game. The game is prepared once from your dump (verified against Redump or a known-compatible content hash), then runs without it.
- Not affiliated with or endorsed by Bandai Namco Entertainment, Sony Interactive Entertainment, Nintendo or any game publisher or developer.
- Licence: GPL v3. Contributions are signed off (DCO) and follow each repository's `CONTRIBUTING.md`.
- **AI-assisted.** A large part of the code, tests, documentation and issues is written by AI agents; the maintainer directs and reviews the work. Mistakes are possible: check what matters to you.

## Contributing

Issues live in each repository's GitHub Issues. To propose a game or platform for the launcher, open a pull request on [catalog](https://github.com/To-Recomp/catalog); only games that have a recomp repository are listed.
