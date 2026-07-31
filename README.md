# 🎬 NaniCLI

NaniCLI 1.8.8 is a Git Bash/Linux/macOS launcher around the full ani-cli 4.15 engine, with NaniCLI aliases and a bundled Node.js crypto helper. It does not require Botan or Python.

## Required dependencies

- Node.js **required** for encrypted source handling
- `curl`, `grep`, `sed`
- `fzf`, `rofi`, or `dmenu`
- `mpv`, `iina`, or `vlc`
- Downloads: `aria2c` plus `yt-dlp` or `ffmpeg`
- Optional: `syncplay`, `ani-skip`

## Windows / Git Bash with Scoop

Run dependency installation in PowerShell:

```powershell
scoop install git nodejs fzf ffmpeg mpv yt-dlp aria2
```

Use Windows Terminal with a Git Bash profile. Then install NaniCLI through your NavineDevs Scoop bucket/release.

After replacing a GitHub release asset:

```powershell
scoop update
scoop uninstall nani-cli
scoop cache rm nani-cli
scoop install nani-cli
```

Open a fresh Git Bash tab and test:

```bash
hash -r
nani-cli --nani-doctor
nani-cli -h
nani-cli "one piece"
```

## Linux

```bash
sudo apt update
sudo apt install -y nodejs curl grep sed fzf mpv aria2 ffmpeg yt-dlp
chmod +x nani-cli nani-engine nani-crypto.js
sudo cp nani-cli nani-engine nani-crypto.js /usr/local/bin/
sudo mkdir -p /usr/local/share/man/man1
sudo cp nani-cli.1 /usr/local/share/man/man1/
```

The three executable files must remain in the same directory.

## macOS

```bash
brew install node curl grep aria2 ffmpeg git fzf yt-dlp
brew install --cask iina
chmod +x nani-cli nani-engine nani-crypto.js
cp nani-cli nani-engine nani-crypto.js "$(brew --prefix)/bin/"
cp nani-cli.1 "$(brew --prefix)/share/man/man1/"
```

## Commands

All original ani-cli commands are supported:

```text
-c, --continue
-d, --download
-D, --delete
-l, --logview
-s, --syncplay
-S, --select-nth NUMBER
-q, --quality QUALITY
-v, --vlc
-V, --version
-h, --help
-e, --episode RANGE
-r, --range RANGE
--dub
--rofi
--dmenu
--skip
--skip-title TITLE
--no-detach
--exit-after-play
-N, --nextep-countdown
-U, --update
```

NaniCLI additions:

```text
--history
--random [query]
--nani-version
--nani-doctor
--nani-help
```

Examples:

```bash
nani-cli
nani "one piece"
nani-cli -q 1080p "frieren"
nani-cli -d -e 1-12 "anime title"
nani-cli --continue
nani-cli --history
nani-cli --random
nani-cli --dub "anime title"
nani-cli -s "anime title"
```

## Troubleshooting

### `Program "botan" not found`

You are running an older release. Reinstall this package and confirm:

```bash
grep -Rni botan ~/scoop/apps/nani-cli/current
```

The rebuilt release should return no executable Botan dependency.

### `Episode is released, but no valid sources!`

This means the live source returned no playable links. First update NaniCLI, clear cache, and retry without forcing quality:

```bash
rm -rf ~/.cache/nani-cli ~/.cache/ani-cli
nani-cli "anime title"
```

Provider websites change independently of NaniCLI, so no static release can guarantee every title/source forever.

## Files

```text
nani-cli
nani-engine
nani-crypto.js
nani-cli.1
README.md
```

## Disclaimer

NaniCLI does not host media. Use it only with content and sources you are authorized to access.

## Credits

Based on ani-cli by pystardust, maintained and extended as NaniCLI by NavineDevs.
