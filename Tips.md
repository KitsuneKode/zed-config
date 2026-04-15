# Zed Tips & Tricks

> Collected tricks, power features, and non-obvious behaviors.
> See `Keybinds.md` for the full shortcut reference.

---

## Multibuffer — Edit Across Files at Once

Zed's most unique feature. Search results open as a **live editable buffer**.

1. `space s g` or `space /` → search project
2. In results, open as multibuffer (button at top or default)
3. Edit directly — changes apply to real files instantly

**Power moves in multibuffer:**
- `g c c` to bulk comment/uncomment across excerpts
- Multi-cursor across all results with `g a` (select all matches)
- `] q` / `[ q` to jump between file excerpts
- Use it for refactoring: search a function name, rename inline everywhere

---

## AI Slash Commands (type `/` in agent chat)

| Command | What it does |
|---------|-------------|
| `/file` | Attach any file as context |
| `/symbols` | All symbols from current file |
| `/diagnostics` | Send all current errors/warnings |
| `/selection` | Current selection |
| `/fetch <url>` | Fetch a URL (docs, APIs, GitHub raw) |
| `/terminal-output` | Last terminal output |
| `/tab` | All open tabs as context |

**`@` inline references** — use inside your message:
- `@filename` — attach a specific file
- `@symbol_name` — attach a specific function/class
- `@diagnostics` — current errors inline

**Workflow:** Before asking the agent to fix a bug, type:
```
/diagnostics fix these errors in @src/api.ts
```
Zero manual copying.

---

## AI Inline Assist Tips (ctrl-k)

- Select a block of code first, then `ctrl-k` — the assistant edits only that selection
- In terminal, `ctrl-k` opens a prompt bar — describe what command you need, it writes it, `ctrl-enter` to run
- In insert mode, `ctrl-k` triggers mid-typing — useful for "complete this function"
- After inline edit, `Tab` accepts, `Escape` rejects

---

## Vim Tricks You Might Miss

### `cx` — Exchange / Swap two regions
```
cx iw    → mark first word (cursor stays)
cx iw    → on second word → they swap positions
```
Works with any motion: `cx i(`, `cx as`, etc. No register juggling.

### `gR` — Replace with register (paste without losing clipboard)
```
yiw           → yank word A
viw gR        → replace word B with A — clipboard still has A
viw gR        → replace word C too
```
Normal `p` in visual would overwrite your clipboard. `gR` doesn't.

### `g c` — Comment as a text object/motion
```
g c c         → toggle comment current line
g c j         → comment current + next line
g c i f       → comment inside function
v i f g c     → visual select function → comment
```

### Visual block = multi-cursor on columns
```
ctrl-v        → enter visual block
j j j         → select 3 lines
I             → insert at start of each line
A             → append at end of each line
```
Use for: adding prefixes, aligning assignments, bulk editing structured data.

### Marks — instant bookmarks within session
```
m a           → set mark 'a' at cursor
' a           → jump to mark 'a'
' '           → jump back to last position (before last jump)
' .           → last edit location
```
Best use: `m a` at a reference location, go explore, `' a` to return.

### `*` and `#` — search current word
```
*             → search forward for word under cursor
#             → search backward
```
Then `n` / `N` to navigate. Combine with `g a` (select all matches) for multi-cursor rename.

### `%` — jump between matching brackets
Works on `()`, `[]`, `{}`, and HTML tags.

### `g ;` / `g ,` — jump through change history
Navigate to where you were last editing without using marks.

---

## Git Panel (native — faster than lazygit for daily work)

- **Stage hunks, not whole files**: In the gutter, click the colored bar next to a change → stage just that hunk
- **Inline blame**: Already enabled — hover over the blame text to see full commit message + author
- `] h` / `[ h` → jump between hunks without leaving the editor
- `space g h r` → restore (revert) current hunk
- `space g h R` → restore entire file
- `space g h d` → expand all diff hunks inline
- `:G` in vim command mode → open git panel

**Workflow for quick commits:**
1. `] h` to review each change
2. `space g h r` to discard junk hunks
3. `:G` → stage + commit in the panel
4. Save lazygit (`space r l`) for rebases, stashes, complex history

---

## Per-Project Config — `.zed/` Folder

Create in any project root:

```
my-project/
  .zed/
    settings.json   ← project overrides
    tasks.json      ← project-specific tasks
```

**Example `.zed/settings.json`:**
```json
{
  "tab_size": 4,
  "hard_tabs": true,
  "formatter": "prettier",
  "soft_wrap": "none",
  "languages": {
    "Python": { "tab_size": 4 }
  }
}
```

**Example `.zed/tasks.json`:**
```json
[
  { "label": "dev", "command": "cargo watch -x run", "use_new_terminal": true }
]
```

Commit `.zed/` to the repo so teammates get the same config automatically.

---

## Edit Predictions (AI ghost text — you just enabled it)

| Key | Action |
|-----|--------|
| `Tab` | Accept full prediction |
| `ctrl-→` | Accept one word at a time |
| `Escape` | Dismiss |

**When it shines:**
- After making a change, it predicts the *next* logical edit nearby
- Writing repetitive code (array entries, object keys, similar functions)
- It's not just autocomplete — it understands the edit context

**Tip:** If it's showing when you don't want it, `space u i` toggles inlay hints off temporarily (different from predictions but useful to know).

---

## SSH Remote Development

```bash
zed ssh://user@hostname
zed ssh://user@hostname/path/to/project
```

Full editor on remote — LSP, file tree, terminal, AI, git all work natively.
No extension, no port forwarding, no VS Code server setup.

---

## Collaboration (Pair Programming)

`ctrl-shift-p` → `collab: share project`

- Generates a join link
- Anyone with Zed can join, see your cursor, edit live
- Shared terminal included
- Works on real files

---

## Project Panel Tips (your neo-tree setup)

- `/` in the panel → search/filter files in current directory
- `-` → go up to parent directory
- `space e` from anywhere → toggle and focus panel simultaneously
- The panel respects `.gitignore` automatically

---

## Useful Ex Commands (vim `:` mode)

| Command | Action |
|---------|--------|
| `:E` or `:Explore` | Open project panel |
| `:G` | Open git panel |
| `:AI` | Open AI panel |
| `:term` | Open terminal |
| `:vs` / `:sp` | Vertical / horizontal split |
| `:<number>` | Jump to line number |
| `:%s/foo/bar/` | Substitute (global by default in Zed) |
| `:sort` | Sort selected lines |
| `:join` or `:j` | Join lines |

---

## Which-Key (you have it enabled)

Press `space` in normal mode and wait — a popup shows all your leader bindings.
Same works for `]`, `[`, `g`, `z` — press and pause to see what's available.
Great for discovering Zed's built-in vim defaults you haven't memorized yet.

---

## Things Worth Exploring Later

- **Jupyter notebooks** — Zed supports `.ipynb` if you work with Python/data
- **DAP debugger** — built-in debug adapter, no extension needed for most languages
- **Zed extensions page** — check monthly, ecosystem is growing fast
- **`zed .`** from terminal — open current directory instantly
- **Multiple project roots** — drag a second folder into the sidebar for monorepo work
- **`ctrl-shift-p` → `dev: open key context view`** — shows active contexts at cursor, useful for debugging why a keybind isn't working
