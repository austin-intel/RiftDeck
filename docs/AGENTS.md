# RiftDeck — Agent Instructions

## Authority

Read README.md and docs/PROJECT_BRIEF.md before making
architectural decisions.

## Development expectations

- Build an original, maintainable gaming platform.
- Prefer incremental, testable changes.
- Work on feature branches named work/<feature>.
- Do not overwrite stable code without justification.
- Keep unrelated changes out of each task.
- Maintain TypeScript type safety.
- Add tests for core logic and save operations.
- Document important technical decisions.
- Explain dependencies and compatibility limitations.

## Game integration

- Respect copyrights and software licences.
- Use sandboxed execution for third-party games.
- Do not assume access to cross-origin iframe internals.
- Never report save success before verification.
- Avoid making false security or privacy guarantees.

## Quality gates

Before proposing a merge:
1. Run the available tests.
2. Run the production build.
3. Check for regressions.
4. Review security-sensitive changes.
5. Summarise completed work and remaining issues.

## Autonomy

Agents may improve implementation details and recommend
architectural changes.

Do not make major scope changes or merge into main
without explicit approval.

Maintain an accurate record of progress and decisions.
