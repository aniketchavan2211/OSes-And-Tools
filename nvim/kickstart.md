# Neovim 

Official GitHub Repo: [kickstart.NVIM](https://github.com/nvim-lua/kickstart.nvim)

copy paste ready made nvim config file.

if `~/.config/nvim` does not create then create one.
```bash
mdkir -p ~/.config/nvim/
```

Then Clone git repo of kickstart.

```bash
git clone https://github.com/nvim-lua/kickstart.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim
```

On initial opening might take time to download plugins( Add-ons / Extensions ).


**Issues** :
- `lua_ls` not found 

Install Required package:

```ash
# For Alpine Linux System
apk search lua-language-server
apk add lua-language-server
```

Fix it by replace `lua_ls` with `lua-language-server`

Edit `init.lua`, search for
```lua
ensure_installed = {
  "lua_ls",
  ...
}
```

Replace with :

```lua
enusre_installed = {
  "lua-language-server",
  ...
}
```

> [!note]
Issue might get fixed. If not then it will be another sort of problems.
