# Copy path

## Introduction

This plugin came from working with react json translations files. This enables
easy and fast access to deeply nested json properties.

Also, I extended it to work with json objects in javascript, just in case
someone else has this requirement.

## Requirements

- [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter)

## Demo

https://github.com/FelipeSanchezSoberanis/copy-path/assets/59965745/e80b3a7b-da0c-45cf-b01a-56b0dd770797

## Example configuration

Create key mappings per file type bound to the current buffer. The `register`
field of the table can be changed to any register that you prefer.

```lua
local copy_path = require("copy-path")

vim.api.nvim_create_autocmd({"FileType"}, {
    pattern = {"json"},
    callback = function(args)
        vim.keymap.set("n", "<leader>cp", function()
            copy_path.copy_json_path({register = "*"})
        end, {buffer = args.buf})
    end
})

vim.api.nvim_create_autocmd({"FileType"}, {
    pattern = {"javascript", "typescript", "javascriptreact", "typescriptreact"},
    callback = function(args)
        vim.keymap.set("n", "<leader>cp", function()
            copy_path.copy_javascript_path({register = "*"})
        end, {buffer = args.buf})
    end
})
```
