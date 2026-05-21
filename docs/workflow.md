# Recommended workflow

## Daily editing

1. **Open / find** — `space space` (file finder); `space /` (project search).
2. **Navigate code** — Vim motions; `K` hover; `]d` / `[d` for diagnostics.
3. **Refactor in one file** — `ctrl-k` inline assist on selection.
4. **Multi-file work** — `space a` agent panel; add context with `ctrl-shift-l` or panel actions.
5. **Run project** — `space r d` dev, `space r t` test; `space r r` for build/lint/typecheck when scripts exist.
6. **Review Git** — Git panel, project diff, or `space g` lazygit when you want a terminal UI.
7. **Everything else** — `space ;` command palette (multibuffers, git graph, outline, settings).

## Agent workflow

1. **Scope context** — selection, file, or terminal output into the thread.
2. **Ask for a bounded change** — one feature or fix per thread when possible.
3. **Review diffs** — accept/reject in editor; do not auto-allow all tools.
4. **Verify** — run `space r t` or `space r c` after substantive edits.
5. **Iterate** — paste failures or logs back into the agent thread.
6. **Revert if needed** — Git panel or `lazygit` before starting a new thread.

Tool runs use **confirm** by default (`agent.tool_permissions.default`). Approve terminal and write tools deliberately.

## When to use what

| Goal | Prefer |
|------|--------|
| Rename / format / code action | `space c r` / `space c f` / `space c a` |
| All errors in project | `space d` → multibuffer |
| Find references | `g r` (Vim default) or palette |
| Long-running dev server | `space r d` (task, dedicated terminal) |
| Quick Git graph / blame | Command palette → Git features |
| Project-specific agent rules | Repo `AGENTS.md`, not this config |

## Validate after editing config

1. Reload Zed.
2. Help → Show Logs (no keymap/settings parse errors).
3. `dev: open key context view` on a binding that misbehaves.
4. Spawn each `space r *` task once in a repo that defines the scripts.
