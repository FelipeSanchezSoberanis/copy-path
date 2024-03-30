# Demo

![Copy path demo](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExaXE4MXVsYnh0YWtrNjNtcjFua2JvMGl0OHN6aG55dDEwdTNlaHgyNyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/POkYJ3hAFYuTkf8I6b/giphy.gif)

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
