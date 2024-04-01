# Demo

https://github.com/FelipeSanchezSoberanis/copy-path/assets/59965745/e80b3a7b-da0c-45cf-b01a-56b0dd770797

# Example configuration

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
