# RiftDeck

**A browser-native gaming platform.**

RiftDeck is an independent, Steam-inspired platform designed to provide a polished gaming library, reliable session management, privacy-conscious features, and connected gaming experiences.

**Status** · Pre-alpha. The source baseline and project site are set up. The RiftDeck launcher is in development.

[Open RiftDeck](https://austin-intel.github.io/RiftDeck/) · [Foundation milestone](https://github.com/austin-intel/RiftDeck/issues/1)

## Upstream foundation

RiftDeck starts from [Katsugachi’s Solus MS](https://github.com/Katsugachi/Solus-MS), pinned to [`891144b`](https://github.com/Katsugachi/Solus-MS/commit/891144ba6f86c4f12b9bc3ef6006efb378a84302). The `upstream/solus-ms` submodule checks out the complete upstream source from [Austin’s fork](https://github.com/austin-intel/Solus-MS). Use it as the baseline for reviewing and migrating launcher features.

See the [upstream notes](docs/UPSTREAM_SOLUS.md) and [project brief](docs/PROJECT_BRIEF.md).

## Run the project site locally

```sh
git clone --branch work/foundation --recurse-submodules https://github.com/austin-intel/RiftDeck.git
cd RiftDeck
python -m http.server 8000 --bind 127.0.0.1 --directory docs
```

Open <http://127.0.0.1:8000/>. GitHub Pages serves the same static files from `docs/`. To populate the Solus MS source in an existing clone, run `git submodule update --init --recursive`. The full upstream checkout is intended for development and is outside the Pages publishing folder.

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

Solus MS is by Katsugachi and declares Apache-2.0. Its original licence and credits are preserved in the pinned source checkout. Third-party game packages and assets require their own redistribution review.
