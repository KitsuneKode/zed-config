# Zed-first config with Vim muscle memory

Personal [Zed](https://zed.dev) configuration: Vim editing habits, a small leader map, Cursor-style AI shortcuts, and native Zed workflows — not a LazyVim port.

## Philosophy

- **Zed stays Zed** — Agent Panel, Inline Assist, multibuffers, project search, Git panel, tasks, and the command palette are the main tools.
- **Vim for editing** — modal editing, relative line numbers, and a compact `space` leader for daily actions.
- **Small surface area** — only keybindings you use often; everything else lives in the command palette or Zed defaults.
- **Repo-specific agents** — project behavior belongs in each repo’s `AGENTS.md` / `.rules`, not in this global config.

## Files

| File | Purpose |
|------|---------|
| `settings.json` | Editor, Vim, theme, agent defaults |
| `keymap.json` | Custom shortcuts (JSONC) |
| `tasks.json` | Bun-first dev/test/build tasks |
| `Keybinds.md` | Active bindings + removed LazyVim-style maps |
| `docs/workflow.md` | Daily and agent workflows |
| `docs/operating-guide.md` | How to operate this config day-to-day |
| `docs/examples/AGENTS.project.example.md` | Template for project-level agent rules |
| `AGENTS.md` | Notes for maintainers editing this repo |

## Kept from Neovim / LazyVim habits

- Vim mode (`vim_mode`, relative line numbers)
- Leader map for file finder, search, docks, LSP, tasks
- `K` hover, `]d` / `[d` diagnostics, `]h` / `[h` hunks
- `jk` to leave insert mode
- `ctrl-s` save (normal) / save-after-normal (insert & visual)
- Terminal `lazygit` task

## Intentionally not copied

- Telescope / Trouble / Neo-tree / Harpoon clones
- Sneak on `s` / `S`, subword `w` / `b` / `e` / `ge`
- `ctrl-d` / `ctrl-u` / `n` / `N` + centering via `SendKeystrokes`
- Large `space` prefix trees (`space f f`, `space w`, `space x`, tab numbers)
- Fragile `SendKeystrokes` chains where a native action exists
- Remapped core Vim motions without a strong reason

## Native Zed features to learn

| Feature | Typical access |
|---------|----------------|
| Agent Panel | `space a`, `ctrl-l` |
| Inline Assist | `ctrl-k` |
| Multibuffers | `space /`, `space d`, references → multibuffer |
| Project Search | `space /` |
| File Finder | `space space` |
| Git Panel / Project Diff / Git Graph | Command palette |
| Tasks | `space r …` or command palette → Tasks |
| Terminal Threads | Agent panel + terminal context |
| Command Palette | `space ;` |

## Agent setup

- **Base keymap:** `Cursor` (AI-friendly defaults)
- **Tool permissions:** `agent.tool_permissions.default` = `confirm` (prompt before tools run)
- **Active external agents:** `cursor`, `opencode`, `claude-acp`, `codex-acp` (registry). Add others in `settings.json` if needed.

## Tasks (Bun-first)

Defined in `tasks.json`. Scripts must exist in the project `package.json` (e.g. `dev`, `test`, `build`, `typecheck`, `lint`).

| Task | Command |
|------|---------|
| lazygit | `lazygit -p $ZED_WORKTREE_ROOT` |
| dev (bun) | `bun run dev` |
| test (bun) | `bun test` |
| build (bun) | `bun run build` |
| typecheck (bun) | `bun run typecheck` |
| lint (bun) | `bun run lint` |

Per-project overrides: `.zed/tasks.json` in the repo.

## Install

```bash
git clone https://github.com/KitsuneKode/zed-config.git ~/.config/zed
# or symlink individual files
```

Reload Zed after changes (`zed: reload` or restart).

## Validate config

1. **Logs** — Help → Show Logs; look for JSON/keymap parse errors.
2. **Keymap** — Command palette → `zed: open keymap` / `dev: open key context view`.
3. **JSONC** — Comments and trailing commas are allowed; do not run strict `jq` on JSONC files without a JSONC-aware parser.
4. **Tasks** — Every `task_name` in `keymap.json` must match a `label` in `tasks.json`.

## Theme

Dark: **Tokyo Night**. Font: **MonoLisa**. Custom theme assets live in `themes/` (e.g. Rxyhn).
