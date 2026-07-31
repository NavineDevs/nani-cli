# 🎬 NaniCLI

NaniCLI is a terminal application for browsing, watching, and downloading anime. It bundles an ani-cli-compatible engine and adds NaniCLI commands, aliases, diagnostics, and a Node.js crypto helper.

**Version:** 1.8.8  
**Platforms:** Linux, macOS, and Windows through Git Bash

## Required dependencies

**Node.js is required to run NaniCLI.** NaniCLI uses the included `nani-crypto.js` helper instead of Python or Botan.

Base requirements:

- Node.js
- curl
- sed and grep
- fzf, rofi, or dmenu
- mpv, IINA, or VLC

Downloads additionally require `aria2c` and either `yt-dlp` or `ffmpeg`.

## Files in the release

- `nani-cli` — launcher and NaniCLI commands
- `nani-engine` — complete ani-cli-compatible engine
- `nani-crypto.js` — Node.js crypto helper
- `nani-cli.1` — manual page
- `README.md` — installation and command reference

## Linux installation

```bash
sudo apt update
sudo apt install -y nodejs curl grep sed aria2 ffmpeg git fzf yt-dlp mpv
chmod +x nani-cli nani-engine nani-crypto.js
sudo cp nani-cli nani-engine nani-crypto.js /usr/local/bin/
sudo cp nani-cli.1 /usr/local/share/man/man1/
```

The three executable files must remain in the same directory.

## macOS installation

```bash
brew install node curl grep aria2 ffmpeg git fzf yt-dlp mpv
chmod +x nani-cli nani-engine nani-crypto.js
cp nani-cli nani-engine nani-crypto.js "$(brew --prefix)/bin/"
cp nani-cli.1 "$(brew --prefix)/share/man/man1/"
```

IINA may be used instead of mpv:

```bash
brew install --cask iina
```

## Windows installation with Scoop and Git Bash

Install Git Bash, Node.js, and dependencies:

```powershell
scoop install git nodejs fzf ffmpeg mpv yt-dlp aria2
```

NaniCLI is a shell application. Run it from **Git Bash** or configure the Scoop shim to launch it through Git Bash.

## Complete command reference

```text
-c, --continue, --history Continue watching from history
-d, --download            Download instead of playing
-D, --delete              Delete watch history
-e, --episode RANGE       Select episode or range
-r, --range RANGE         Alias for --episode
-q, --quality QUALITY     Select best, worst, 360p, 480p, 720p, or 1080p
-S, --select-nth NUMBER   Automatically select the nth result
-v, --vlc                 Use VLC
-s, --syncplay            Use Syncplay
--dub                     Search dubbed releases
--random                  Randomly select from results
--rofi                    Use rofi
--dmenu                   Use dmenu
--skip                    Use ani-skip with mpv
--skip-title TITLE        Override the ani-skip title
--no-detach               Keep mpv attached
--exit-after-play         Exit after playback
-N, --nextep-countdown    Show next-episode countdown
-l, --logview             Show logs
-U, --update [branch]     Run the upstream engine updater
-V, --version             Show engine version
-h, --help                Show complete help
--nani-version            Show NaniCLI and engine versions
--nani-doctor             Check files and dependencies
--nani-help               Show NaniCLI-specific help
```

Examples:

```bash
nani-cli "one piece"
nani "frieren" -q 1080p
nani-cli --dub "dragon ball"
nani-cli --random
nani-cli --history
nani-cli -d -e 1-3 "cowboy bebop"
nani-cli --nani-doctor
```

## Configuration

NaniCLI accepts ani-cli environment variables, including:

```bash
export ANI_CLI_PLAYER=mpv
export ANI_CLI_QUALITY=1080p
export ANI_CLI_DOWNLOAD_DIR="$HOME/Downloads/anime"
```

On Windows, set the download folder from PowerShell and reopen Git Bash:

```powershell
setx ANI_CLI_DOWNLOAD_DIR "%USERPROFILE%\Downloads\anime"
```

## Disclaimer

NaniCLI does not host content. Only use it with sources and media you are authorized to access.

## Credits

Based on `ani-cli` by pystardust. Maintained and extended as NaniCLI by NavineDevs.
