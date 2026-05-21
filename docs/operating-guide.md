# How to operate this config

Quick reference for what you have **after** the lean pass. Reload Zed after pulling changes.

## Layout

| Side | Panel |
|------|--------|
| Left | Project tree, outline (button visible), Git panel |
| Center | Editor |
| Right | Agent panel |
| Bottom | Terminal (`` ctrl-` `` or `space t`) |

## Daily flow

1. **Open** — `space space` (file finder) or `ctrl-shift-o` (recent projects).
2. **Search project** — `space /` → edit in multibuffer.
3. **Edit** — Vim as usual; `jk` leaves insert; `ctrl-s` saves.
4. **Errors** — `] d` / `[ d` in file; `space d` for all diagnostics in multibuffer.
5. **Run** — `space r d` dev server; `space r t` tests; `space r r` for build/lint/typecheck/lazygit list.
6. **AI** — `ctrl-k` small edit; `space a` / `ctrl-l` agent panel; `ctrl-shift-l` send selection.
7. **Git** — Git panel (left) for stage/commit; `space g` lazygit when you need history/rebase; palette → `git: diff` for project diff.
8. **Anything else** — `space ;` command palette.

## AI keys (one job each)

| Key | Job |
|-----|-----|
| `ctrl-k` | Inline assist (selection or prompt) |
| `ctrl-l` | Toggle agent panel |
| `ctrl-shift-l` | Add selection to current thread |

No `ctrl-i` — same as `ctrl-k`, removed to avoid duplicate.

## Tasks

| Key | Runs |
|-----|------|
| `space r d` | `bun run dev` (terminal, stays open) |
| `space r t` | `bun test` |
| `space r r` | Menu: build, lint, typecheck, lazygit, … |
| `space g` | lazygit |

Scripts must exist in the project `package.json`. Non-Bun repos: use `space r r` or add `.zed/tasks.json` in the project.

## Pane focus

| Key | Direction |
|-----|-----------|
| `ctrl-h` | Left |
| `ctrl-j` | Down |
| `ctrl-shift-k` | Up |

**Right pane:** command palette → `pane: focus right` (no `ctrl-l` — that’s agent).

## External agents (all four enabled)

In the agent panel, pick provider/thread:

- **cursor**
- **opencode** (default model in settings)
- **claude-acp**
- **codex-acp**

Tool runs ask for confirmation (`agent.tool_permissions.default: confirm`).

## Settings behavior worth knowing

| Setting | Effect |
|---------|--------|
| `format_on_save: lsp` | Format via LSP/formatter, not forced Prettier everywhere |
| Markdown | No edit predictions; no trim trailing whitespace on save |
| Terminal | Bar cursor; shape can follow shell when supported |
| Minimap | Off; scrollbar auto |
| Outline | Button shown on left |

## Native Zed features (palette, not keybound)

| Want | Palette command |
|------|-----------------|
| Git graph | `git graph` |
| Project diff | `git: diff` |
| Find references | `find all references` |
| Go to definition | `go to definition` |
| Focus right pane | `pane: focus right` |
| Format now | `format` |

## Troubleshooting

- Binding dead? `dev: open key context view` at cursor.
- Parse errors? Help → Show Logs.
- Task missing? Label in `tasks.json` must match `task_name` in keymap exactly.

See also: `Keybinds.md`, `docs/workflow.md`.
