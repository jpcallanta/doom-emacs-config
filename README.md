# Doom Emacs Configuration

My personal [Doom Emacs](https://github.com/doomemacs/doomemacs)
configuration.

## Contents

| File | Purpose |
| --- | --- |
| `init.el` | Enabled Doom modules |
| `config.el` | Personal settings (font, theme, UI, behavior) |
| `packages.el` | Extra packages installed on top of Doom's defaults |
| `.gitignore` | Keeps local Emacs state and build artifacts out of the repo |

## Setup
                             
```sh
git clone <repo-url> ~/.config/doom
doom sync
```

Restart Emacs afterwards. The config expects the **JetBrainsMono Nerd Font**
(size 20); install it, or adjust `doom-font` and `doom-variable-pitch-font` in
`config.el`.

## Highlights

- **Completion:** `corfu +orderless` with `vertico`
- **Editing:** `evil +everywhere`, `file-templates`, `fold`, `snippets`,
  `whitespace +guess +trim`
- **Emacs:** `dired`, `electric`, `tramp`, `undo`, `vc`, `format +lsp`
- **Languages:** Emacs Lisp, Lua, Markdown, Odin (+LSP), Org, Shell
- **Markdown:** `.md` files open in `md-mode`; `C-c C-v`
  (`md-mode-toggle-markup`) toggles the rendered view. In `markdown-mode`
  buffers, local leader `v` toggles between edit and rendered view via
  `my/toggle-markdown-view`
- **Checkers:** on-the-fly `syntax` checking
- **Tools:** `lsp +eglot`, `magit`, `eval +overlay`, `lookup`
- **UI:** `doom-gruvbox` theme, `dashboard`, `modeline`, `popup +defaults`,
  `hl-todo`, `ophints`, `vc-gutter +pretty`, `vi-tilde-fringe`, `workspaces`,
  90% background opacity, relative line numbers
- **Org:** notes live in `~/org/`
- **Config:** `default +bindings +smartparens`

## Notes

- `confirm-kill-emacs` and `confirm-kill-processes` are disabled, so Emacs
  quits without prompting even if sub-processes (LSP, terminals) are running.
- The `macos` module is only enabled when running on macOS.
- `config.el` overrides Doom's default of opening README files in `gfm-mode`,
  so `README.md` opens in `md-mode` like other `.md` files.
- `md-mode` is installed from GitHub and pinned to a specific commit in
  `packages.el`. To update it, replace the `:pin` hash (or unpin it
  temporarily) and run `doom sync`.
