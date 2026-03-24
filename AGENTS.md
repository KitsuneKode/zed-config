# AGENTS.md

This folder is a personal Zed configuration with Vim mode enabled and keymaps tuned toward LazyVim muscle memory.

## What matters here

- `settings.json` controls editor behavior, fonts, panels, formatter setup, and the base keymap.
- `keymap.json` is the main customization layer and should stay focused on LazyVim-style navigation without breaking the user's Cursor-style AI flow.
- `themes/` contains custom theme assets and is usually unrelated to shortcut work.

## Current editing rules

- Keep `base_keymap` as `Cursor` unless the user explicitly asks to change the AI workflow.
- Preserve `ctrl-i` and the existing `space a ...` AI shortcuts because they match the user's current habits.
- Keep `ctrl-s` behaving like this:
  in normal mode it saves,
  in insert or visual mode it returns to normal mode and then saves.
- Keep `ctrl-shift-l` mapped to select all matches, matching VS Code behavior.
- Prefer narrow Vim-specific contexts over broad `Editor && !menu` bindings so modal behavior is not accidentally overridden.

## When editing keymaps

- Favor changes that match LazyVim expectations for panes, buffers, search, and leader mappings.
- Avoid removing established shortcuts unless they clearly conflict with the user's stated workflow.
- Reload Zed after keymap changes if behavior seems unchanged.
