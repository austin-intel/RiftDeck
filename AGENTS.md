# RiftDeck — Repository Agent Instructions

These instructions apply repository-wide. The earlier `docs/AGENTS.md` is retained for continuity; this file takes precedence if they diverge.

## Read first

- `README.md`
- `docs/PROJECT_BRIEF.md`
- `docs/UPSTREAM_SOLUS.md` (when present)

## Project direction

RiftDeck is an original, browser-native game platform that **uses the current Katsugachi/Solus-MS launcher as its upstream reference and potential migration baseline**. Preserve provenance, follow licence terms, and do not copy third-party game ports or commercial assets without verified redistribution rights. Keep upstream source imports isolated and reviewable; avoid blindly rewriting code.

## Development workflow

- Protect `main`; work on `work/*` branches.
- Make small, testable changes with clear commit messages.
- Keep user data and existing files intact.
- Maintain TypeScript type safety and automated tests.
- Record tested behaviour, known limitations, and upstream SHA when syncing.
- Submit pull requests for review; do not merge into `main` without approval.

## Browser integration and privacy

- Use permission-appropriate, sandboxed game adapters.
- Do not assume cross-origin iframe access or universal save support.
- Verify persistence before reporting a save as complete.
- Be explicit about browser-history and administrator-monitoring limits.
- Build responsible local privacy and instant session suspension features; do not implement monitoring bypass.

## Quality gates

Before proposing a merge: run available tests and production build, inspect critical browser security controls, document failures, and summarise changes.
