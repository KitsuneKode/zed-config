# Agent Instructions (example — copy into a project repo)

Place this as `AGENTS.md` (or use `.rules` / Cursor rules) **in the project repository**, not in `~/.config/zed`. Zed and Cursor agents read repo-local instructions when working in that tree.

Below is an example shaped for a Bun CLI project (e.g. Kunai). Adapt sections to your stack.

---

# Agent Instructions

This is **YourProject** — a terminal-first CLI. Describe what the app does in one paragraph.

## Runtime

- Prefer Bun-native APIs where practical.
- Prefer `Bun.spawn`, `Bun.which`, and `Bun.sleep` over Node equivalents when appropriate.
- Do not add heavy dependencies without justification.

## Domain rules (example: media / playback)

- Do not break mpv IPC lifecycle tracking.
- Do not mark content completed from ambiguous network EOF.
- Preserve player supervision behavior.
- Treat HLS/network stalls differently from intentional playback completion.

## Code style

- Keep CLI startup fast.
- Keep terminal UX responsive.
- Prefer small, reviewable patches.
- Explain risky changes before editing.

## Validation

After editing:

- `bun test`
- `bun run typecheck` (if present)
- `bun run lint` (if present)

## Out of scope

- Do not change global editor config in `~/.config/zed` unless asked.
- Do not refactor unrelated modules in the same PR as a bugfix.

---

## Usage

1. Copy relevant sections into `AGENTS.md` at the project root.
2. Keep instructions short and enforceable — agents follow explicit constraints better than long essays.
3. Update when architecture or safety rules change.
