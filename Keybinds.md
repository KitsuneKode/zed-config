# Keybindings

Zed-first map with Vim muscle memory. `base_keymap: Cursor` still applies for unlisted defaults.

Run `zed: open default keymap` for the full built-in list.

## AI / Agent

| Key | Context | Action |
|-----|---------|--------|
| `ctrl-k` | Normal / Insert / Visual / Terminal / Editor | Inline assist |
| `ctrl-l` | Normal / Insert | Toggle agent panel |
| `ctrl-shift-l` | Editor / Visual | Add selection to agent thread |
| `ctrl-shift-a` | Editor | Select all matches |
| `space a` | Vim leader | Toggle right dock (agent) |
| `ctrl-\` | AgentPanel | Close agent panel |
| `ctrl-n` | AgentPanel | New thread |
| `ctrl-shift-h` | AgentPanel | Thread history |
| `ctrl-alt-p` | AgentPanel | Manage profiles |

## Panes & docks

| Key | Context | Action |
|-----|---------|--------|
| `ctrl-h` | Dock / Terminal / Editor | Focus pane left |
| `ctrl-j` | Dock / Terminal / Editor | Focus pane down |
| `ctrl-shift-k` | Dock / Terminal / Editor | Focus pane up |
| `` ctrl-` `` | Workspace / Editor / Terminal | Toggle bottom dock (terminal) |
| `space e` | Vim leader / empty pane | Toggle left dock (project) |
| `space t` | Vim leader | Toggle bottom dock |
| `space a` | Vim leader | Toggle right dock (agent) |

**Pane right:** no dedicated key (`ctrl-l` is agent). Use command palette → `pane: focus right` or click the pane.

## Leader (`space`)

| Key | Action |
|-----|--------|
| `space space` | File finder |
| `space /` | Project search |
| `space e` | Project panel (left) |
| `space a` | Agent panel (right) |
| `space t` | Terminal (bottom) |
| `space ;` | Command palette |
| `space c a` | Code actions |
| `space c r` | Rename |
| `space d` | Diagnostics (multibuffer) |
| `space g` | Task: lazygit |
| `space r r` | Task picker (build, lint, typecheck, …) |
| `space r d` | Task: dev (bun) |
| `space r t` | Task: test (bun) |

Format on save uses LSP — no `space c f` binding.

## LSP / Git in editor

| Key | Action |
|-----|--------|
| `K` | Hover |
| `] d` / `[ d` | Next / previous diagnostic |
| `] h` / `[ h` | Next / previous hunk |

## Insert / visual / save

| Key | Context | Action |
|-----|---------|--------|
| `j k` | Insert | Escape to normal |
| `ctrl-s` | Normal | Save |
| `ctrl-s` | Insert / Visual | Normal then save |
| `shift-j` / `shift-k` | Visual | Move line down / up |

## Project panel

| Key | Action |
|-----|--------|
| `j` / `k` | Next / previous |
| `h` / `l` | Collapse / expand |
| `enter` | Open file |
| `a` / `shift-a` | New file / directory |
| `r` / `d` | Rename / delete |
| `q` / `escape` | Close dock / unfocus |

## Global

| Key | Action |
|-----|--------|
| `ctrl-shift-o` | Recent projects |
| `ctrl-c` / `ctrl-v` / `ctrl-x` / `ctrl-a` | Copy / paste / cut / select all |

## Via task picker only (`space r r`)

| Task label | Command |
|------------|---------|
| build (bun) | `bun run build` |
| lint (bun) | `bun run lint` |
| typecheck (bun) | `bun run typecheck` |

## Removed (use palette / picker instead)

| Was | Use instead |
|-----|-------------|
| `space f` | `space space` (file finder) |
| `ctrl-i` | `ctrl-k` (inline assist) |
| `ctrl-/` | `` ctrl-` `` (bottom dock) |
| `ctrl-l` pane right | Palette: focus right pane |
| `space r b/l/c` | `space r r` task picker |
| `space c f` | Format on save (`format_on_save: lsp`) |
