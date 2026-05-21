# AGENTS.md

Maintainer notes for this **Zed config repo** (not for application projects).

## Identity

- Zed-first: native Agent Panel, multibuffers, project search, tasks, Git UI.
- Vim mode for editing; small `space` leader — not a LazyVim recreation.

## Files

| File                                      | Role                                                  |
| ----------------------------------------- | ----------------------------------------------------- |
| `settings.json`                           | Theme, Vim, agent permissions, `agent_servers`        |
| `keymap.json`                             | Daily shortcuts only; JSONC with `//` comments        |
| `tasks.json`                              | Bun-first tasks; labels must match keymap `task_name` |
| `Keybinds.md`                             | Human-readable binding list + removed maps            |
| `docs/workflow.md`                        | Daily / agent workflow                                |
| `docs/examples/AGENTS.project.example.md` | Template for **project** repos                        |

## Editing rules

- Keep `base_keymap`: `"Cursor"` unless the user changes AI workflow.
- Keep `ctrl-k`, `space a`, `ctrl-l` AI habits unless asked otherwise (`ctrl-i` removed — duplicate of `ctrl-k`).
- `ctrl-l` is agent toggle only; pane-right uses palette, not `ctrl-l`.
- Keep `ctrl-s`: save in normal; `vim::NormalBefore` then save in insert/visual.
- Keep `ctrl-shift-l` → `agent::AddSelectionToThread`; `ctrl-shift-a` → select all matches.
- Prefer native actions over `workspace::SendKeystrokes`.
- Do not remap core Vim motions (`w`, `b`, `e`, `s`, `S`, etc.) without explicit request.
- Use narrow contexts (`VimControl`, `vim_mode == insert`, …) over broad `Editor && !menu`.
- Project-specific agent behavior belongs in each repo’s `AGENTS.md`, not here.

## Agent settings

- `agent.tool_permissions.default` should stay `"confirm"` (Zed docs; not `"ask"`).
- Minimal `agent_servers`: `cursor`, `opencode`, `claude-acp`, `codex-acp` unless user expands.

## After keymap/task changes

1. Reload Zed.
2. Check logs for parse errors.
3. Confirm every `["task::Spawn", { "task_name": "…" }]` label exists in `tasks.json`.
