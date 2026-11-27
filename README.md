# karazuri extras

[karazuri](https://github.com/karazuri/palette) themes for coding agents, terminals, editors, and command-line tools.

[View the palette](https://karazuri.github.io/palette/)

## Variants

| Variant | Appearance | Background | Description |
|---|---|---|---|
| `umi` | Dark | `#1A1A22` | Sea. Cool blue-gray background. |
| `yoru` | Dark | `#161514` | Night. Darker and warmer than `umi`. |
| `kami` | Light | `#D2CCBC` | Paper. Warm background at about 60% brightness. |

![karazuri umi palette preview](https://raw.githubusercontent.com/karazuri/palette/main/assets/umi.svg)

![karazuri yoru palette preview](https://raw.githubusercontent.com/karazuri/palette/main/assets/yoru.svg)

![karazuri kami palette preview](https://raw.githubusercontent.com/karazuri/palette/main/assets/kami.svg)

### ANSI colors

| Index | Color | `umi` | `yoru` | `kami` |
|---|---|---|---|---|
| 0 | Black | `#14141B` | `#0F0F0E` | `#292830` |
| 1 | Red | `#E8707E` | `#D9787F` | `#892D38` |
| 2 | Green | `#A3C97A` | `#A3B58A` | `#36561D` |
| 3 | Yellow | `#D6B77A` | `#C4AE84` | `#604E22` |
| 4 | Blue | `#82A8E8` | `#8BA4C7` | `#2B497A` |
| 5 | Magenta | `#C4A8F5` | `#B8A3D6` | `#523B83` |
| 6 | Cyan | `#7FC4B4` | `#8FB8AA` | `#22564D` |
| 7 | White | `#C8C093` | `#B5B0A3` | `#CAC3B1` |
| 8 | Bright black | `#ABAAA4` | `#A09A8F` | `#4B4943` |
| 9 | Bright red | `#F2616E` | `#E0616A` | `#981F2E` |
| 10 | Bright green | `#8FB573` | `#94AD7E` | `#34611E` |
| 11 | Bright yellow | `#E8C88A` | `#D9BE8C` | `#674B0F` |
| 12 | Bright blue | `#6FB5D6` | `#79A8C6` | `#20547A` |
| 13 | Bright magenta | `#B8B4D0` | `#BDB3C6` | `#514967` |
| 14 | Bright cyan | `#9ED6D8` | `#9EC3C2` | `#235367` |
| 15 | Bright white | `#E2DCC5` | `#D2CDBF` | `#C8C2B0` |

## How to use

Run the shell commands from the root of the extras repository. The examples use `umi`. Substitute `yoru` or `kami` to use another variant.

### OpenCode

For OpenCode 1.x, install the JSON files from `opencode/`. For the 2.x CLI, use `opencode/v2/`. Use one set per installation because the filenames are the same.

```sh
mkdir -p ~/.config/opencode/themes
cp opencode/karazuri-{umi,yoru,kami}.json ~/.config/opencode/themes/
```

Restart OpenCode and run `/themes` to select `karazuri-umi`, `karazuri-yoru`, or `karazuri-kami`. Each file keeps its own appearance. [OpenCode themes](https://opencode.ai/docs/cli/theme/)

### Codex CLI

Install the TextMate themes into the `themes` directory under `CODEX_HOME`.

```sh
mkdir -p "${CODEX_HOME:-$HOME/.codex}/themes"
cp tmtheme/*.tmTheme "${CODEX_HOME:-$HOME/.codex}/themes/"
```

Run `/theme` to select a karazuri variant. Codex uses it to highlight code and diffs. To match the rest of the session, set your terminal to the same karazuri variant. [Codex CLI themes](https://learn.chatgpt.com/docs/cli-customization#syntax-highlighting-and-themes)

### Claude Code

```sh
mkdir -p ~/.claude/themes
cp claude-code/karazuri-{umi,yoru,kami}.json ~/.claude/themes/
```

Run `/theme` to select a karazuri variant. If you just created the directory, restart Claude Code first. This themes Claude Code's interface colors. Set the same variant in your terminal for the background and to match ANSI output. [Claude Code custom themes](https://code.claude.com/docs/en/terminal-config#create-a-custom-theme)

### Pi

```sh
mkdir -p "${PI_CODING_AGENT_DIR:-$HOME/.pi/agent}/themes"
cp pi/karazuri-{umi,yoru,kami}.json "${PI_CODING_AGENT_DIR:-$HOME/.pi/agent}/themes/"
```

Restart Pi or run `/reload`, then open **Theme** in `/settings` and select a karazuri variant. Use the matching terminal palette for the session background. [Pi themes](https://github.com/earendil-works/pi/blob/main/packages/coding-agent/docs/themes.md)

### Windows Terminal

From PowerShell, install the fragment containing all three schemes.

```powershell
$karazuriFragments = Join-Path $env:LOCALAPPDATA 'Microsoft\Windows Terminal\Fragments\karazuri'
New-Item -ItemType Directory -Force $karazuriFragments | Out-Null
Copy-Item windows-terminal/karazuri.json $karazuriFragments
```

Restart Windows Terminal and set **Color scheme** under a profile's **Appearance** settings. [Windows Terminal fragments](https://learn.microsoft.com/en-us/windows/terminal/json-fragment-extensions)

### JetBrains IDEs

In a JetBrains IDE based on IntelliJ Platform 2024.3 or later, open **Settings → Plugins**, open the gear menu, and choose **Install Plugin from Disk…**. Select [`karazuri.jar`](jetbrains/karazuri.jar) and restart if prompted. Choose a karazuri variant under **Appearance & Behavior → Appearance → Theme**. The plugin includes the UI theme and its linked editor color scheme for each variant. [JetBrains plugin installation](https://www.jetbrains.com/help/idea/managing-plugins.html#install_plugin_from_disk)

### Ghostty

```sh
mkdir -p ~/.config/ghostty/themes
cp ghostty/karazuri-{umi,yoru,kami} ~/.config/ghostty/themes/
```

Set `theme = karazuri-umi` in your Ghostty config for a fixed theme. To follow the system appearance, use this setting instead.

```ini
theme = light:karazuri-kami,dark:karazuri-umi
```

### kitty

```sh
mkdir -p ~/.config/kitty
cp kitty/karazuri-umi.conf ~/.config/kitty/
```

Add this line to `kitty.conf`.

```conf
include karazuri-umi.conf
```

To follow the system appearance in kitty 0.38 or later, install the [automatic theme files](https://sw.kovidgoyal.net/kitty/kittens/themes/#change-color-themes-automatically-when-the-os-switches-between-light-and-dark) and restart kitty.

```sh
mkdir -p ~/.config/kitty
cp kitty/karazuri-umi.conf ~/.config/kitty/dark-theme.auto.conf
cp kitty/karazuri-kami.conf ~/.config/kitty/light-theme.auto.conf
cp kitty/karazuri-kami.conf ~/.config/kitty/no-preference-theme.auto.conf
```

### WezTerm

```sh
mkdir -p ~/.config/wezterm/colors
cp wezterm/karazuri-{umi,yoru,kami}.toml ~/.config/wezterm/colors/
```

Set `config.color_scheme = "karazuri Umi"` in your Lua config for a fixed theme. To [follow the system appearance](https://wezterm.org/config/lua/window/get_appearance.html), add this before your config's return statement.

```lua
local wezterm = require("wezterm")
wezterm.on("window-config-reloaded", function(window)
  local scheme = "karazuri Kami"
  if window:get_appearance():find("Dark") then
    scheme = "karazuri Umi"
  end

  local overrides = window:get_config_overrides() or {}
  if overrides.color_scheme ~= scheme then
    overrides.color_scheme = scheme
    window:set_config_overrides(overrides)
  end
end)
```

### Alacritty

```sh
mkdir -p ~/.config/alacritty
cp alacritty/karazuri-umi.toml ~/.config/alacritty/
```

Add the theme to the `import` list in `alacritty.toml`.

```toml
[general]
import = ["~/.config/alacritty/karazuri-umi.toml"]
```

### iTerm2

```sh
open iterm2/karazuri-umi.itermcolors
```

You can also import the file from **Settings > Profiles > Colors > Color Presets > Import**. Select `karazuri-umi` from Color Presets after importing it. To follow the system appearance, import `iterm2/karazuri-kami.itermcolors` as well and enable **Use separate colors for light and dark mode**. Use the **Editing** control to select `karazuri-kami` for light mode and `karazuri-umi` for dark mode. [iTerm2 color settings](https://iterm2.com/documentation-preferences-profiles-colors.html)

### Helix

```sh
mkdir -p ~/.config/helix/themes
cp helix/karazuri_umi.toml ~/.config/helix/themes/
```

Helix uses the theme selected in `~/.config/helix/config.toml`. Change it manually when you want to switch variants.

```toml
theme = "karazuri_umi"
```

### tmux

```sh
mkdir -p ~/.config/tmux
cp tmux/karazuri-umi.tmux ~/.config/tmux/
```

Add this line to `~/.tmux.conf` or your active tmux config. The theme sets colors and preserves your status-line content.

```tmux
source-file ~/.config/tmux/karazuri-umi.tmux
```

### fzf

```sh
mkdir -p ~/.config/fzf
cp fzf/karazuri-umi.sh ~/.config/fzf/
```

Add this line to your shell config. It appends a `--color` option to `FZF_DEFAULT_OPTS`.

```sh
source ~/.config/fzf/karazuri-umi.sh
```

### bat

```sh
mkdir -p "$(bat --config-dir)/themes"
cp tmtheme/*.tmTheme "$(bat --config-dir)/themes/"
bat cache --build
bat --theme=karazuri-umi README.md
```

### Sublime Text

On macOS, copy the theme into your user packages directory.

```sh
cp tmtheme/karazuri-umi.tmTheme "$HOME/Library/Application Support/Sublime Text/Packages/User/"
```

On other platforms, use **Preferences > Browse Packages** to locate the `User` directory and copy `tmtheme/karazuri-umi.tmTheme` there. Select the theme with **UI: Select Color Scheme** from the Command Palette.

### delta

Install the bat themes first. Delta loads custom syntax themes from the bat cache. [Delta theme documentation](https://dandavison.github.io/delta/supported-languages-and-themes.html)

```sh
mkdir -p ~/.config/delta
cp delta/karazuri.gitconfig ~/.config/delta/
```

Add the include and feature selection to `~/.gitconfig`.

```ini
[include]
    path = ~/.config/delta/karazuri.gitconfig
[delta]
    features = karazuri-umi
```

## Regenerating themes

The theme files are generated from `palette.json` in [karazuri/palette](https://github.com/karazuri/palette). Make color changes there and regenerate the files. With both repositories cloned side by side, run this from the extras repository.

```sh
python3 ../palette/scripts/build.py extras --out .
```

## License

MIT
