# zed-config

Personal Zed configuration with Vim mode enabled, LazyVim-inspired navigation, and Cursor-style AI shortcuts.

## Files

- `settings.json` for editor, UI, formatter, and Vim settings.
- `keymap.json` for custom shortcuts and modal keybindings.
- `themes/` for custom theme assets.
- `AGENTS.md` for concise editing notes and future maintenance context.

## Notable choices

- `base_keymap` stays on `Cursor` to preserve the existing AI workflow.
- `ctrl-i` is kept for inline AI assist.
- `ctrl-s` saves in normal mode and exits to normal mode before saving in insert or visual mode.
- `ctrl-shift-l` selects all matches, similar to VS Code.
- The active theme is `NvChad Rxyhn Theme`. If you want that theme separately, use this repo: `https://github.com/KitsuneKode/nvchad-rxyhn-theme-vscode-cursor-zed`

## Usage

Clone or copy these files into `~/.config/zed/` and reload Zed.
