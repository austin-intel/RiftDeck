# RiftDeck — Project Brief

## 1. Project objective

Build an original, high-quality browser-native gaming platform with a Steam-inspired library, reliable game integrations, sophisticated session management, and a distinctive visual identity.

The product should operate efficiently on ordinary desktop hardware without requiring administrator installation.

## 1A. Upstream baseline and migration strategy

**Baseline:** [Katsugachi/Solus-MS](https://github.com/Katsugachi/Solus-MS) at commit `3b4c652f78b7df347000b17ddc7134896d2840d8` (last observed update 2026-11-08). The repository's declared licence is Apache-2.0.

RiftDeck should evolve from the current Solus-MS launcher rather than discard its existing features. First audit the upstream code and third-party game licensing, then selectively port or adapt suitable launcher functionality. Source imports require attribution, provenance and tests; the project-level licence does not automatically cover every external game, image or port.

Read [UPSTREAM_SOLUS.md](UPSTREAM_SOLUS.md) for the pinned baseline, known architecture, constraints and acceptance gates. The first engineering milestone is an upstream audit and viable migration strategy—not a blind bulk import.

## 2. Product priorities

### P0 — Essential

- Premium, responsive user interface
- Searchable game library
- Game detail pages and collections
- Reliable game launcher
- Compatible-game autosave and recovery
- One-action instant session suspension
- Audio muting and background resource management
- Local-first user settings
- Clear compatibility and error reporting

### P1 — Important

- Playtime statistics
- Player profiles
- Achievements
- Save management
- Game health monitoring
- Offline support for eligible games
- Customisable themes
- Game controller support

### P2 — Future features

- Creator Workshop
- Challenge Hub
- Multiplayer integration
- Cross-device account synchronisation
- Time-Fork Replay Laboratory
- Intergame Wormholes

## 3. Instant Session Suspend

RiftDeck should support a single action that:

1. Immediately replaces the active game view with a preloaded neutral workspace.
2. Disables gameplay input and mutes supported audio.
3. Requests a save snapshot from compatible games.
4. Persists and verifies the save transaction.
5. Releases game resources when safe.
6. Allows users to restore their saved session.

Autosaving must be supported wherever feasible.

Never claim that unsaved progress has been preserved before the save operation succeeds.

Do not claim that the platform can erase browser history or evade managed-device monitoring.

## 4. Architecture

Preferred implementation stack **subject to an upstream migration assessment**:

- React + TypeScript
- Vite
- IndexedDB
- Progressive Web App support
- Modular game adapter API
- Automated unit and browser tests

Prefer a frontend-only MVP. Introduce backend infrastructure only when justified by concrete requirements.

## 5. User experience

- Fast startup and navigation
- Premium dark interface
- Consistent spacing, typography and animation
- Keyboard and mouse accessibility
- Responsive layout
- Clear error messages
- No unnecessary onboarding or excessive configuration

## 6. Engineering principles

- Prioritise reliability over feature count.
- Avoid unnecessary dependencies.
- Protect stable versions.
- Maintain tests for critical behaviour.
- Use original branding and properly licensed assets.
- Sandbox third-party content.
- Respect user privacy and device/network policies.
- Record architectural decisions and known limitations.

## 7. MVP definition

The first MVP is complete when:

- The platform runs locally in a modern browser.
- Users can browse and search the library.
- At least one original or suitably licensed demonstration game launches reliably.
- The integrated demonstration game supports suspend and restore.
- Preferences persist across reloads.
- Basic responsive layouts work.
- Core automated tests pass.
- The application builds successfully for static deployment.

## 8. Development strategy

Build the smallest reliable foundation first.

Develop in feature branches, review changes, run tests, and merge stable milestones into `main`.

AI development agents may recommend changes to this specification when they provide evidence and explain tradeoffs. Major scope changes require project-owner approval.
