# Neovim keybind

## Default keybinds
| Keybind | Action |
|---|---|
| a | Insert mode and set cursor to the right of the current letter |
| i | Insert mode and set cursor to the left of the current letter |
| f + (char) | Search for the first letter that matches char |
| cw | Delete chars from the cursor to the first space and insert mode (Change word) |
| cb | Delete chars from the word behind the cursor and insert mode (Change back word) |
| ct + (char) | Delete chars from the cursor to the char and insert mode (excluding the char) |
| S/cc | Delete the whole line and insert mode (Change line) |
| C/c$  | Change from the cursor to the end of the line |
| s/cl  | Change the current character |
| $ | Go to the end of the line |
| 0/_ | Go to the start of the line |

## How to set custom keybinds
```lua
vim.keymap.set("n", "T", ":Neotree toggle<CR>", { desc = "Open neotree", })
vim.keymap.set("n", "<leader>lp", ":Lazy<CR>", { desc = "Open lazy.nvim", })
```

`vim.keymap.set()` accepts 4 arguments:
1. The mode the keybind is usable in ("n" for normal mode, "i" for insert mode)
2. The keybind to press, can include control characters (<leader>...)
3. The command to run on the press of the keybind.
4. A table of other parameters (Such as the keybind description...)
