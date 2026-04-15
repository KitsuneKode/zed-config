# Zed Keybinds Reference

> LazyVim + Cursor AI workflow — custom keymap
> Run `zed: open default keymap` in the command palette to see ALL Zed defaults on top of these.

---

## AI / Agent (Cursor-style)

| Key | Context | Action |
|-----|---------|--------|
| `ctrl-k` | Normal / Insert / Visual / Terminal | Inline assist (edit/generate) |
| `ctrl-i` | Editor / Terminal | Inline assist (secondary) |
| `ctrl-l` | Normal / Insert | Toggle AI chat panel |
| `ctrl-e` | Normal | Toggle right dock (agent panel) |
| `ctrl-shift-l` | Visual / Editor | Add selection to AI chat thread |
| `space a` | Normal/Visual | Toggle AI agent panel |
| `ctrl-\` | AgentPanel | Close agent panel |
| `ctrl-n` | AgentPanel | New chat thread |
| `ctrl-shift-h` | AgentPanel | View thread history |
| `ctrl-alt-p` | AgentPanel | Manage profiles (Write/Ask/Minimal) |
| `shift-tab` | AgentPanel | **Cycle profiles** — Write → Ask → Minimal *(Zed default)* |
| `ctrl-alt-/` | AgentPanel | Switch AI model *(Zed default)* |
| `alt-tab` | AgentPanel | Cycle favorite models *(Zed default)* |
| `ctrl->` (`ctrl-shift-.`) | Editor (selection) | Add selection as context *(Zed default)* |

> **Note:** `ctrl-k` replaces pane-up. Pane-up is now `ctrl-shift-k`.
> **Profile cycle** matches Cursor's `shift-tab` to rotate between Agent/Normal/Ask modes.

---

## Pane / Window Navigation

| Key | Context | Action |
|-----|---------|--------|
| `ctrl-h` | Editor/Terminal/Dock | Focus pane left |
| `ctrl-l` | Editor/Terminal/Dock | Focus pane right |
| `ctrl-j` | Editor/Terminal/Dock | Focus pane down |
| `ctrl-shift-k` | Editor/Terminal/Dock | Focus pane up |
| `space w v` / `space \|` | Editor | Split right |
| `space w s` / `space -` | Editor | Split down |
| `space w q` | Editor | Close active item |
| `space w c` / `space w d` | Editor | Close all items in pane |
| `ctrl-/` / `` ctrl-` `` | Anywhere | Toggle terminal (bottom dock) |
| `space t` / `space f t` | Editor | Toggle terminal |

---

## File / Buffer

| Key | Action |
|-----|--------|
| `space space` / `space f f` | File finder (fuzzy) |
| `space f r` / `space f p` | Recent projects |
| `space f n` / `space b n` | New file |
| `space ,` | Tab switcher |
| `space b b` | Alternate file (last buffer) |
| `space b d` | Close current buffer |
| `space b o` | Close other buffers |
| `space b q` | Close all buffers |
| `shift-h` | Previous tab |
| `shift-l` | Next tab |
| `] b` / `[ b` | Next / previous tab |
| `space 1`–`space 9` | Jump to tab by number |
| `space 0` | Jump to last tab |
| `ctrl-6` (ProjectPanel) | Alternate file |

---

## Explorer (Project Panel — neo-tree)

| Key | Action |
|-----|--------|
| `space e` | Toggle file explorer |
| `-` | Focus explorer / select parent dir |
| `a` / `%` | New file |
| `shift-a` | New directory |
| `r` / `shift-r` | Rename |
| `d` / `shift-d` | Delete |
| `x` | Cut |
| `c` / `y` | Copy |
| `p` | Paste |
| `h` | Collapse entry |
| `l` | Expand entry |
| `j` / `k` | Navigate up/down |
| `g g` / `shift-g` | First / last item |
| `o` / `enter` / `t` / `v` | Open file |
| `q` / `escape` | Close / unfocus explorer |
| `/` | Search in directory |
| `:` | Command palette |

---

## Search

| Key | Action |
|-----|--------|
| `space /` / `space s g` | Project-wide search |
| `space f g` | Project search |
| `space s b` | Buffer search (vim /) |
| `space s w` | Buffer search deploy |
| `space s s` | Outline / symbols in file |
| `space s d` | Diagnostics panel |
| `space n` | Clear search highlights |
| `n` / `shift-n` | Next/prev result (auto-centers) |

---

## LSP / Code Intelligence

| Key | Action |
|-----|--------|
| `K` | Hover documentation |
| `g d` | Go to definition *(Zed default)* |
| `g D` | Go to declaration *(Zed default)* |
| `g y` | Go to type definition *(Zed default)* |
| `g I` | Go to implementation *(Zed default)* |
| `g r` / `g A` | Find all references |
| `g s` | Find symbol in file *(Zed default)* |
| `g S` | Find symbol in project *(Zed default)* |
| `g h` | Show inline error / hover *(Zed default)* |
| `g .` | Code actions (alternative) *(Zed default)* |
| `space c a` | Code actions |
| `space c r` | Rename symbol |
| `space c f` | Format file |
| `space l d` | Diagnostics panel |
| `] d` / `[ d` | Next/prev diagnostic |
| `] e` / `[ e` | Next/prev error (alias) |

---

## Diagnostics / Trouble

| Key | Action |
|-----|--------|
| `space x x` | Open diagnostics panel |
| `space x d` | Go to next diagnostic |
| `] d` / `[ d` | Navigate diagnostics |

---

## Git

| Key | Action |
|-----|--------|
| `space g g` | Lazygit (spawns task) |
| `space g b` | Git blame |
| `space g h d` | Expand all diff hunks |
| `space g h D` | Git diff view |
| `space g h r` | Restore hunk |
| `space g h R` | Restore file |
| `] h` / `] c` | Next hunk *(] c is Zed default)* |
| `[ h` / `[ c` | Previous hunk *([ c is Zed default)* |

---

## Vim Motions (Zed extensions)

| Key | Action |
|-----|--------|
| `w` / `b` / `e` | Subword start/start-back/end (camelCase/snake_case aware) |
| `g e` | Subword end backward |
| `s` + 2 chars | Sneak forward (like leap.nvim) |
| `S` + 2 chars | Sneak backward |
| `] m` / `[ m` | Next/prev function *(Zed default)* |
| `] ]` / `[ [` | Next/prev section *(Zed default)* |
| `] /` / `[ /` | Next/prev comment *(Zed default)* |
| `[ x` / `] x` | Shrink/expand syntax node *(Zed default)* |
| `ctrl-d` / `ctrl-u` | Scroll half page + center |

---

## Text Objects (Zed extras)

| Key | Action |
|-----|--------|
| `i f` / `a f` | Function body / function *(Zed default)* |
| `i c` / `a c` | Class body / class *(Zed default)* |
| `i a` / `a a` | Argument / list item *(Zed default)* |
| `i t` / `a t` | HTML tag *(Zed default)* |
| `b` (after `d`/`c`/`v` etc.) | Any brackets (custom) |
| `g s` (visual) | Add surround (since `S` = sneak) |
| `ys` / `cs` / `ds` | Surround add/change/delete *(Zed default)* |
| `g c` | Toggle comment / comment object *(Zed default)* |
| `g R` | Replace with register *(Zed default)* |

---

## Multi-cursor

| Key | Action |
|-----|--------|
| `g l` | Add cursor for next word copy *(Zed default)* |
| `g L` | Add cursor for prev word copy *(Zed default)* |
| `g a` | Select all word copies *(Zed default)* |
| `g >` / `g <` | Skip and add next/prev word *(Zed default)* |
| `ctrl-shift-a` | Select all matches (custom) |

---

## Toggle Features

| Key | Action |
|-----|--------|
| `space u i` | Toggle inlay hints |
| `space u w` | Toggle soft wrap |
| `space m p` | Markdown preview |
| `space m P` | Markdown preview to side |

---

## Insert Mode

| Key | Action |
|-----|--------|
| `j k` / `j j` | Escape to normal mode |
| `ctrl-s` | Save and stay in insert |
| `ctrl-k` | Inline AI assist |
| `ctrl-l` | Toggle AI panel |
| `ctrl-x ctrl-o` | Open completion menu *(Zed default)* |
| `ctrl-x ctrl-a` | Inline AI suggestion *(Zed default)* |
| `ctrl-x ctrl-l` | Code actions *(Zed default)* |

---

## Visual Mode

| Key | Action |
|-----|--------|
| `shift-j` / `shift-k` | Move line down/up |
| `alt-j` / `alt-k` | Move line down/up (normal too) |
| `ctrl-k` | Inline AI on selection |
| `ctrl-shift-l` | Add selection to AI chat |
| `g s` | Add surround |

---

## Misc / Global

| Key | Action |
|-----|--------|
| `space q q` | Quit Zed |
| `space ;` / `space :` | Command palette |
| `ctrl-shift-p` | Command palette *(Zed default)* |
| `ctrl-s` | Save (normal mode) |
| `shift-y` | Yank to end of line |
| `ctrl-c` / `ctrl-v` / `ctrl-x` | Copy / Paste / Cut (restored) |
| `ctrl-a` | Select all |
| `ctrl-6` | Alternate file (last buffer) |

---

## Ex Commands (vim `:` palette)

| Command | Action |
|---------|--------|
| `:w` / `:wq` / `:q` | Save / save+close / close |
| `:vs` / `:sp` | Vertical / horizontal split |
| `:tabnew` / `:tabn` / `:tabp` | New tab / next / prev |
| `:E` or `:Explore` | Open project panel |
| `:G` or `:Git` | Open git panel |
| `:AI` | Open AI panel |
| `:term` | Open terminal |
| `:<number>` | Jump to line |
| `:%s/foo/bar/` | Substitute (global by default in Zed) |

---

## Tasks (space r — run tasks)

| Key | Action |
|-----|--------|
| `space r r` | Task picker (choose any task) |
| `space r l` | lazygit |
| `space r d` | Dev server (bun) |
| `space r t` | Run tests |
| `space r b` | Build |

> Tasks defined in `~/.config/zed/tasks.json`. Per-project tasks go in `.zed/tasks.json`.

---

## Recent Projects

| Key | Context | Action |
|-----|---------|--------|
| `ctrl-shift-o` | Anywhere | Open recent projects |
| `space f r` / `space f p` | Editor | Recent projects |

---

## TODO / To Investigate

- [ ] `ctrl-[` / `ctrl-]` in AgentPanel — cycle between chat threads (action name unknown)
- [ ] `ctrl-shift-backspace` — cancel AI generation in chat (action name unknown)
- [ ] Window resize keybinds — Zed has no pane resize action via keyboard yet
- [ ] `space u` expand — more toggles (line numbers, git gutter, etc.)
- [ ] `space g s` — git status panel integration
- [ ] Harpoon-style file marks — Zed doesn't have this natively, investigate extensions
- [ ] `ctrl-r` in normal mode — redo (verify it works; should be Zed default)
- [ ] Debug panel keybinds — if/when DAP is used
- [ ] Verify `ctrl-e` doesn't conflict with vim scroll-down-one-line in operator mode
- [ ] Check if `agent::NewThread` is the correct action name for new AI chat
- [ ] `space g c` — git commit from within Zed git panel workflow
