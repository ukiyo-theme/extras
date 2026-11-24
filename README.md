# Ukiyo extras

[Ukiyo](https://github.com/ukiyo-theme/palette) themes for terminals and command-line tools. Each folder has one file per variant: `umi` (dark), `yoru` (darker, muted) and `kami` (light, about 60% brightness).

| Tool | Folder |
|---|---|
| Ghostty | [`ghostty/`](ghostty) |
| kitty | [`kitty/`](kitty) |
| WezTerm | [`wezterm/`](wezterm) |
| Alacritty | [`alacritty/`](alacritty) |
| iTerm2 | [`iterm2/`](iterm2) |
| Helix | [`helix/`](helix) |
| tmux | [`tmux/`](tmux) |
| fzf | [`fzf/`](fzf) |
| delta | [`delta/`](delta) |
| bat and Sublime Text | [`tmtheme/`](tmtheme) |

The terminal themes use the same 16 ANSI colors as the Neovim port's terminal.

## Install

The examples use `umi`. Swap in `yoru` or `kami` for the other variants.

### Ghostty

Copy the files to `~/.config/ghostty/themes/`, then add to your Ghostty config:

```
theme = light:ukiyo-kami,dark:ukiyo-umi
```

### kitty

Copy a file to `~/.config/kitty/` and add `include ukiyo-umi.conf` to `kitty.conf`.

### WezTerm

Copy the files to `~/.config/wezterm/colors/`, then set the scheme by its name:

```lua
config.color_scheme = "Ukiyo Umi"
```

### Alacritty

Add the file to the `import` list in `alacritty.toml`:

```toml
[general]
import = ["~/.config/alacritty/ukiyo-umi.toml"]
```

### iTerm2

Open **Settings > Profiles > Colors > Color Presets > Import** and choose an `.itermcolors` file. Then pick it from the same menu.

### Helix

Copy the files to `~/.config/helix/themes/` and set `theme = "ukiyo_umi"` in `config.toml`.

### tmux

Add `source-file /path/to/ukiyo-umi.tmux` to `~/.tmux.conf`. It sets colors only, not your status-line content.

### fzf

Source the file from your shell config:

```sh
source /path/to/fzf/ukiyo-umi.sh
```

It appends a `--color` option to `FZF_DEFAULT_OPTS`.

### bat

```sh
mkdir -p "$(bat --config-dir)/themes"
cp tmtheme/*.tmTheme "$(bat --config-dir)/themes/"
bat cache --build
bat --theme=ukiyo-umi README.md
```

For Sublime Text, copy a `.tmTheme` file into your `Packages/User` folder and select it under **UI: Select Color Scheme**.

### delta

Install the bat themes first, since delta uses them for syntax highlighting. Then add to `~/.gitconfig`:

```ini
[include]
    path = /path/to/delta/ukiyo.gitconfig
[delta]
    features = ukiyo-umi
```

## Changing the colors

Don't edit these files by hand. They are generated from `palette.json` in [ukiyo-theme/palette](https://github.com/ukiyo-theme/palette):

```sh
python3 ../palette/scripts/build.py extras --out .
```

The path assumes both repos are cloned side by side.

## License

MIT
