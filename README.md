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
```
