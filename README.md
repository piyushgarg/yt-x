# yt-x

![GitHub Issues or Pull Requests](https://img.shields.io/github/issues/Benex254/yt-x)
![GitHub License](https://img.shields.io/github/license/Benex254/yt-x)
![GitHub file size in bytes](https://img.shields.io/github/size/Benex254/yt-x/yt-x)
![GitHub Release](https://img.shields.io/github/v/release/Benex254/yt-x)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/Benex254/yt-x)

Browse YouTube from your terminal.
Plus other sites yt-dlp supports.

[yt-x.webm](https://github.com/user-attachments/assets/d4aa3329-c009-4625-84a6-390519595648)

<details>
<summary>Workflow Demo</summary>
https://www.reddit.com/r/unixporn/comments/1hou2s7/oc_ytx_v040_workflow_new_year_new_way_to_explore/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button
</details>

## Features

- **Interactive Menu**: Text-based UI using `fzf` or `rofi` for seamless navigation.
- **YouTube-Specific Menus**: Access your feed, trending videos, playlists, watch later, subscriptions feed, liked videos, clips.
- **Playback Support**: Play videos and audio via `mpv` or `vlc`.
- **Search Functionality**: Search for videos, channels and playlists directly.
- **Channel Exploration**: Explore channels, including their videos, streams, podcasts, shorts, and playlists.
- **Saved Channels**: Bookmark your favorite channels for quick access, with support for importing existing subscriptions.
- **Saved Videos**: Save videos to watch later.
- **Mixes**: Generate and explore YouTube song mixes.
- **Custom Playlists**: Save playlists for easier access.
- **Download Management**: Download videos, audio, and playlists using `yt-dlp`.
- **History & Recents**: Track your recent videos and search history.
- **Configuration Management**: Customize and manage configurations for yt-x, mpv and yt-dlp with ease.
- **Extensions:** Extend yt-x with your own custom ui and preview logic allowing more precise coverage of other sites that yt-dlp supports🥳
- **Custom Commands:** Basically a simple way to achieve the same thing with extensions. A custom command is just a yt-dlp command that loads a playlist or playlist like json.
- **Miscellaneous Features**:
  - Shell completions for `bash`, `zsh`, and `fish`.
  - Desktop entry generation for easy access.

## Installation

![Linux/BSD](https://img.shields.io/badge/-Linux/BSD-red.svg?style=for-the-badge&logo=linux)
![Arch Linux](https://img.shields.io/badge/-Arch_Linux-black.svg?style=for-the-badge&logo=archlinux)
![MacOS](https://img.shields.io/badge/-MacOS-lightblue.svg?style=for-the-badge&logo=apple)
![Android](https://img.shields.io/badge/-Android-green.svg?style=for-the-badge&logo=android)

```bash
# NixOS
nix profile install github:Benexl/yt-x

# Latest Release
curl -sL "https://raw.githubusercontent.com/Benexl/yt-x/refs/tags/<latest-release-tag>/yt-x" -o ~/.local/bin/yt-x && chmod +x ~/.local/bin/yt-x

# Development Version
curl -sL "https://raw.githubusercontent.com/Benexl/yt-x/refs/heads/master/yt-x" -o ~/.local/bin/yt-x && chmod +x ~/.local/bin/yt-x
```

## Dependencies

### Required

- [jq](https://github.com/jqlang/jq) - JSON parsing.
- [curl](https://curl.se/) - Download preview images.
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) - Fetch YouTube data.
- [fzf](https://github.com/junegunn/fzf) - Main UI navigation.
- [mpv](https://mpv.io/) - Video and audio playback.
- [ffmpeg](https://www.ffmpeg.org/) - Proper HLS stream downloading.
- [bash](https://www.gnu.org/software/bash/) - Script interpreter.

### Optional

- [gum](https://github.com/charmbracelet/gum) - Enhanced UI (highly recommended).
- [chafa](https://github.com/hpjansson/chafa) - Cross-terminal image rendering (highly recommended).
- [icat](https://sw.kovidgoyal.net/kitty/) - Image rendering.
- [imgcat](https://github.com/danielgatis/imgcat) - Image rendering.
- [rofi](https://github.com/davatorium/rofi) - Alternate UI.

---

## Usage

```bash
# Launch the UI
yt-x

# Edit configuration
yt-x -e

# Specify player at runtime
yt-x --player <mpv/vlc>

# Set selector at runtime
yt-x -s <fzf/rofi>

# Specify Rofi theme path
yt-x --rofi-theme <path>

# Enable/disable preview
yt-x --preview / yt-x --no-preview

# Print desktop entry
yt-x -E

# Print shell completions
yt-x completions --bash
yt-x completions --zsh
yt-x completions --fish

# Update the script
yt-x --update

# Display help
yt-x --help
```

---

## Tips

### Enabling Imports of Subscriptions & Private Playlists

Set your preferred browser in the configuration file:

```ini
PREFERRED_BROWSER: chrome
```

To enable `mpv` to access private playlists and videos, add this to `mpv.conf`:

```ini
ytdl-raw-options=cookies-from-browser=chrome
ytdl-format="best[height=1080]/bestvideo[height=1080]+bestaudio/best[height=720]/bestvideo[height=720]+bestaudio/best"
```

For additional enhancements, consider:

- [uosc](https://github.com/tomasklaen/uosc) for a modern `mpv` UI.
- [thumbfast](https://github.com/po5/thumbfast) for thumbnail timeline previews.

## Custom Playlists

Define custom playlists by editing `~/.config/yt-x/custom_playlists.json` (or use the UI):

```json
[
  {
    "name": "<playlist name>",
    "playlistUrl": "https://www.youtube.com/playlist?list=<playlist-id>",
    "playlistWatchUrl": "https://www.youtube.com/watch?list=<playlist-id>"
  }
]
```

## Contribution

Pull requests are highly welcome!

## Support

Need help? Join the community on Discord:

<p align="center">
<a href="https://discord.gg/HBEmAwvbHV">
<img src="https://invidget.switchblade.xyz/C4rhMA4mmK">
</a>
</p>

## Supporting the Project

Give the project a star and consider contributing to the codebase.

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Y8Y8ZAA7N)
