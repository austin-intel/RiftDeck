# RiftDeck

**A browser-native gaming platform.**

RiftDeck is an independent, Steam-inspired platform designed to provide a polished gaming library, reliable session management, privacy-conscious features, and connected gaming experiences.

**Status:** Pre-alpha — planning and architecture.

## Upstream foundation

RiftDeck starts from the **Katsugachi/Solus-MS launcher** as a version-pinned reference and prospective migration base, not a from-scratch clone. The upstream source is at commit [`3b4c652`](https://github.com/Katsugachi/Solus-MS/commit/3b4c652f78b7df347000b17ddc7134896d2840d8) (8 November 2026), under a repository-level Apache-2.0 licence. Launcher-code reuse requires appropriate attribution, and embedded third-party game ports and assets have separate rights considerations.

See [upstream baseline and import gates](docs/UPSTREAM_SOLUS.md) and the [project brief](docs/PROJECT_BRIEF.md). The upstream snapshot is **documented but not yet copied into RiftDeck**; a source, licence and integration audit comes first.

## Vision

Build a sophisticated web gaming ecosystem that runs in modern browsers without requiring administrator installation.

RiftDeck aims to combine:

- A modern Steam-inspired game library
- Search, favourites, collections and game profiles
- Reliable game launching and compatibility checks
- Instant session suspension and supported-game autosaving
- Local-first privacy and storage management
- Optional offline gameplay for compatible games
- Achievements, personal statistics and challenges
- A standard integration system for browser games
- Experimental cross-game experiences

## Core principles

1. **Quality:** Build a professional, responsive interface.
2. **Reliability:** Protect game progress and preserve stable releases.
3. **Performance:** Minimise loading times and resource usage.
4. **Privacy:** Avoid unnecessary tracking and provide transparent data controls.
5. **Compatibility:** Support modern desktop browsers and a range of devices.
6. **Originality:** Develop an independent architecture, identity and user experience.
7. **Security:** Use sandboxing and validate third-party integrations.
8. **Responsible access:** Respect software licences, network policies and device-management restrictions.

## Initial technology direction

- TypeScript
- React
- Vite
- IndexedDB for local storage
- Progressive Web App support
- Modular game adapters
- Automated testing and GitHub Actions

The final architecture may change after examining the current Solus-MS code and the risks of an immediate framework migration.

## Development roadmap

### V0.1 — Foundation
Game library, navigation, search, game pages, collections, basic launching and session suspension.

### V0.2 — Player experience
Profiles, statistics, integrated saves and achievements.

### V0.3 — Reliability
Game compatibility checks, performance controls and optional offline support.

### V0.4 — Ecosystem
Creator integrations, challenges and extensible game APIs.

### V1.0 — First stable release
Polished platform with tested core features and a distinctive integrated-game experience.

## Development workflow

- `main` — stable development baseline
- `work/*` — feature and engineering branches
- Pull requests — changes reviewed before integration
- GitHub Issues — features, bugs and engineering tasks

Do not overwrite stable releases or remove historical evidence without explicit review.

## Credits and licensing

RiftDeck is an independent project. Referenced third-party platforms are design inspiration only. Game assets and external software must have appropriate distribution rights.

A project licence will be selected before public release.
