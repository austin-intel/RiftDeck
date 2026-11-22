# Upstream Baseline — Katsugachi/Solus-MS

The complete original source is available through the `upstream/solus-ms` Git submodule. It sits outside the `docs/` folder served by RiftDeck’s project site.

## Exact source

- [Original repository](https://github.com/Katsugachi/Solus-MS) and [Austin’s fork](https://github.com/austin-intel/Solus-MS)
- [Pinned commit `891144ba6f86c4f12b9bc3ef6006efb378a84302`](https://github.com/Katsugachi/Solus-MS/commit/891144ba6f86c4f12b9bc3ef6006efb378a84302), at the head of both repositories’ `main` branches when selected on 23 November 2026 (Sydney time)
- [Upstream Apache-2.0 licence](https://github.com/Katsugachi/Solus-MS/blob/891144ba6f86c4f12b9bc3ef6006efb378a84302/LICENSE) and [README](https://github.com/Katsugachi/Solus-MS/blob/891144ba6f86c4f12b9bc3ef6006efb378a84302/README.md)

After cloning RiftDeck, run `git submodule update --init --recursive` to fetch the pinned sources. The original [`3b4c652`](https://github.com/Katsugachi/Solus-MS/commit/3b4c652f78b7df347000b17ddc7134896d2840d8) research pin remains part of the project history. Record and review any future submodule pin changes.

## Observed architecture

Upstream has a mostly monolithic HTML/CSS/JavaScript launcher, game wrappers and images, and a service worker. Its README describes a searchable library, themes, local persistence, statistics and a mobile UI. Some wrappers load remote resources and some files bundle substantial third-party content. Review each game and asset separately before republishing it.

Upstream’s entry page restricts runtime to listed deployment origins, displays a request against deploying Solus MS forks to GitHub Pages, and includes third-party analytics. RiftDeck’s current Pages site serves its own project landing page and links to the authorised upstream launcher.

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

## Migration acceptance gate

Before incorporating upstream code into the RiftDeck app:

- [ ] Record the upstream SHA and changed files (no ambiguity about provenance).
- [ ] Inspect launcher `index.html` and dependencies, including remote URLs, external scripts and game content.
- [ ] Check the permissions for each file to be redistributed; treat third-party ports separately from the repo-level Apache licence.
- [ ] Preserve Apache-2.0 licence, relevant notices, and document modifications for reused covered code.
- [ ] Remove or isolate any deployment-specific assumptions and unwanted analytics in a reviewable way.
- [ ] Test locally with an original or permissively licensed demonstration game before expanding imports.
- [ ] Ensure RiftDeck has its own branding, documented source credits, and a functioning minimal build.

## Build sequencing

**Phase A — baseline audit:** Review the pinned source, build a licence manifest and map features for migration.

**Phase B — compatible foundation:** Scaffold the RiftDeck application and migrate reviewed game-library functionality with tests. A justified incremental HTML-first approach is acceptable if React conversion would create unnecessary regression risk.

**Phase C — differentiated features:** Local-first profiles, game-health reporting, save vault, session suspension for integrated games and additional platform features.

## Important limitations

A regular website cannot clear Chrome browsing history, erase administrator logs, guarantee that external games can be paused/saved, or close arbitrary tabs. Any privacy or save claims must reflect tested browser behaviour.
