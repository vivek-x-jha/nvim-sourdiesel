# sourdiesel

A Neovim colorscheme that reads colors from your env file and applies highlight groups.

## Layout
```
sourdiesel/
├─ colors/
│  └─ sourdiesel.lua        # Entry point for :colorscheme sourdiesel
└─ lua/
   └─ sourdiesel/
      └─ init.lua           # Implementation (verbatim from your lua/sourdiesel.lua)
```

## Installation

### Native packpath
Clone into your `pack/*/start` (autoload) or `pack/*/opt` (optional) directory:

```sh
# Start (loads on startup)
git clone <your-repo-url> ~/.config/nvim/pack/schemes/start/sourdiesel

# OR: Opt (requires :packadd)
git clone <your-repo-url> ~/.config/nvim/pack/schemes/opt/sourdiesel
```

If installed under `opt`, add in your config:
```lua
vim.cmd.packadd('sourdiesel')
```

### Neovim 0.12+ vim.pack
```lua
vim.pack.add({ url = 'https://github.com/<you>/sourdiesel', name = 'sourdiesel' })
```

### lazy.nvim
```lua
{ 'you/sourdiesel', name = 'sourdiesel', priority = 1000, lazy = false }
```

## Usage
```lua
vim.cmd.colorscheme('sourdiesel')
```

`colors/sourdiesel.lua` sets:
```lua
vim.g.colors_name = 'sourdiesel'
require('sourdiesel').setup()
```

## Notes
- Highlights live in `lua/sourdiesel/init.lua` (content copied verbatim from your uploaded file).
- If your palette is read from `$HOME/.zshenv`, ensure that file exists on the target machine.
- Recommended: avoid forcing user options (like `termguicolors`) inside the scheme.

## Initialize Git
```sh
cd sourdiesel
git init -b main
git add .
git commit -m "feat: initial commit (colorscheme scaffold)"
git remote add origin git@github.com:<you>/sourdiesel.git
git push -u origin main
```
