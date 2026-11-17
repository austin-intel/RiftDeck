# Upstream Baseline — Katsugachi/Solus-MS

**Status:** Pinned research and migration reference; source has **not** been imported into RiftDeck yet.

## Exact source

- Repository: https://github.com/Katsugachi/Solus-MS
- Default branch: `main`
- Pinned commit: `3b4c652f78b7df347000b17ddc7134896d2840d8`
- Commit URL: https://github.com/Katsugachi/Solus-MS/commit/3b4c652f78b7df347000b17ddc7134896d2840d8
- Latest observed upstream push: **2026-11-08 06:22:03 UTC**
- Snapshot selected for RiftDeck: **2026-11-17** (the latest verified upstream commit on that date)
- Project-level declared licence: **Apache License 2.0**; see https://github.com/Katsugachi/Solus-MS/blob/3b4c652f78b7df347000b17ddc7134896d2840d8/LICENSE
- README: https://github.com/Katsugachi/Solus-MS/blob/3b4c652f78b7df347000b17ddc7134896d2840d8/README.md

Pin the above SHA for initial investigation. Later upstream changes require explicit comparison and a new documented decision; do not silently track the moving head of `main`.

## Observed architecture

The repository has **68 root entries**, consisting of **33 HTML files**, **33 image/icon files**, `README.md` and `LICENSE`, with no directories in the observed root listing. The main `index.html` is approximately **157 KB** and contains a largely monolithic HTML/CSS/JavaScript launcher.

The upstream README describes a searchable web-game library, themes and local-storage persistence, statistics, game wrappers/iframes, mobile UI and browser-specific session options. Individual HTML game wrappers may reference substantial third-party assets hosted elsewhere. This means the repository's size, Apache licence and browser-native form do **not** establish that all included game ports, images or remote binaries are ours to redistribute.

The present `index.html` begins with an origin allowlist for specified upstream deployments, and includes third-party analytics. These and all external destinations need a security/privacy audit before importing or deploying altered code. The README's local Python-server instructions may conflict with its origin allowlist; do not assert untested local compatibility.

## RiftDeck development decision

RiftDeck should **evolve from the verified Solus-MS launcher experience and, after an explicit licence/security review, reuse appropriate upstream launcher code** rather than building an unrelated product. Retain recognisable and useful baseline functionality while developing original branding and differentiated architecture.

Suggested feature parity and migration inventory:

1. Catalogue and searchable game-library UX
2. Game detail cards and curated collections
3. Responsive layout and theme persistence
4. Per-game launch/status information
5. Basic user preferences and optional local statistics
6. Sandboxed game adapters for appropriately licensed games
7. Verified save, pause, suspend and resume for cooperating games

**Excluded from unreviewed imports:** third-party game packages and images without verified rights; unwanted third-party tracking; origin-based deployment restrictions; methods intended to bypass school/device monitoring, masquerade as schoolwork, or make misleading privacy promises.

## Import acceptance gate

Before importing original code, the implementation agent must:

- [ ] Record the upstream SHA and changed files (no ambiguity about provenance).
- [ ] Inspect launcher `index.html` and dependencies, including remote URLs, external scripts and game content.
- [ ] Check the permissions for each file to be redistributed; treat third-party ports separately from the repo-level Apache licence.
- [ ] Preserve Apache-2.0 licence, relevant notices, and document modifications for reused covered code.
- [ ] Remove or isolate any deployment-specific assumptions and unwanted analytics in a reviewable way.
- [ ] Test locally with an original or permissively licensed demonstration game before expanding imports.
- [ ] Ensure RiftDeck has its own branding, documented source credits, and a functioning minimal build.

## Build sequencing

**Phase A — baseline audit:** Source review, licence manifest and migration matrix. No blind copy or site deployment.

**Phase B — compatible foundation:** Scaffold the RiftDeck application and migrate reviewed game-library functionality with tests. A justified incremental HTML-first approach is acceptable if React conversion would create unnecessary regression risk.

**Phase C — differentiated features:** Local-first profiles, game-health reporting, save vault, session suspension for integrated games and additional platform features.

## Important limitations

A regular website cannot clear Chrome browsing history, erase administrator logs, guarantee that external games can be paused/saved, or close arbitrary tabs. Any privacy or save claims must reflect tested browser behaviour.
