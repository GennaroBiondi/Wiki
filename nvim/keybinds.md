# Neovim keybind

## Default keybinds
| Keybind     | Action                                                       |
| ----------- | ------------------------------------------------------------ |
| `a`         | Enter insert mode **after** the cursor                       |
| `i`         | Enter insert mode **before** the cursor                      |
| `f<char>`   | Jump forward to the next occurrence of `<char>` on the line  |
| `t<char>`   | Jump forward **just before** the next occurrence of `<char>` |
| `cw`        | Change from cursor to the end of the current word            |
| `cb`        | Change from cursor back to the beginning of the current word |
| `ct<char>`  | Change until `<char>` (character itself not included)        |
| `cc` / `S`  | Change the whole line                                        |
| `C` / `c$`  | Change from cursor to end of line                            |
| `cl` / `s`  | Change one character                                         |
| `$`         | Move cursor to end of line                                   |
| `0`         | Move cursor to start of line                                 |
| `^`         | Move cursor to first non-blank character of line             |
| `o`         | Open new line below and enter insert mode                    |
| `O`         | Open new line above and enter insert mode                    |
| `l`         | Move cursor right (normal mode)                              |
| `h`         | Move cursor left (normal mode)                               |
| `k`         | Move cursor up (normal mode)                                 |
| `j`         | Move cursor down (normal mode)                               |
| `yy`        | Copy (yank) the whole line                                   |
| `y{motion}` | Copy (yank) text covered by the motion (e.g., `yw`)          |

## How to set custom keybinds
```lua
-- Examples
vim.keymap.set("n", "T", ":Neotree toggle<CR>", { desc = "Open neotree", })
vim.keymap.set("n", "<leader>lp", ":Lazy<CR>", { desc = "Open lazy.nvim", })
```

`vim.keymap.set()` accepts 4 arguments:
1. The mode the keybind is usable in (see [[keybinds#Modes]])
2. The keybind to press, can include control characters [[keybinds#Control characters]]
3. The command to run on the press of the keybind.
4. A table of other parameters (Such as the keybind description...)

### Control characters
| Notation          | Meaning                                       |
| ----------------- | --------------------------------------------- |
| `<leader>`        | Leader key (user-defined prefix, default `\`) |
| `T`               | Capital **T** key                             |
| `<C-x>`           | `Ctrl` + `x`                                  |
| `<S-x>`           | `Shift` + `x`                                 |
| `<A-x>` / `<M-x>` | `Alt` + `x` (Meta)                            |
| `<CR>`            | Enter / Return                                |
| `<Esc>`           | Escape key                                    |
| `<Tab>`           | Tab key                                       |
| `<Space>`         | Space key                                     |
| `<BS>`            | Backspace                                     |

### Modes
| Mode | Meaning               |
| ---- | --------------------- |
| `n`  | Normal mode           |
| `i`  | Insert mode           |
| `v`  | Visual mode           |
| `x`  | Visual selection mode |
| `t`  | Terminal mode         |
| `c`  | Command-line mode     |
