# 🎬 NaniCLI

NaniCLI is an terminal application for browsing, watching, and downloading anime.

This release uses **OpenSSL** for encrypted source handling. It does **not** require Botan, Node.js, or Python.

## Included files

- `nani-cli` — launcher, aliases, diagnostics, and combined help
- `nani-engine` — full ani-cli-compatible engine with OpenSSL provider decryption
- `nani-cli.1` — manual page

Keep `nani-cli` and `nani-engine` in the same folder.

## Dependencies

Required:

- Bash-compatible shell
- `openssl`
- `curl`
- `grep`
- `sed`
- `fzf`, `rofi`, or `dmenu`
- `mpv`, IINA, or VLC

For downloads:

- `aria2c`
- `yt-dlp` or `ffmpeg`

Optional:

- `syncplay` for `-s`
- `ani-skip` for `--skip`
- `patch` for upstream `-U` updates

## Windows — Scoop and Git Bash

Run in PowerShell:

```powershell
scoop bucket add extras
scoop install git openssl fzf ffmpeg mpv yt-dlp aria2
```

Use the **Git Bash profile inside Windows Terminal**. After installing the Scoop package/release, run:

```bash
nani-cli --nani-doctor
nani-cli -h
nani-cli "one piece"
```

## Linux — Debian/Ubuntu

```bash
sudo apt update
sudo apt install -y openssl curl grep sed fzf mpv aria2 ffmpeg yt-dlp patch
chmod +x nani-cli nani-engine
sudo cp nani-cli nani-engine /usr/local/bin/
sudo cp nani-cli.1 /usr/local/share/man/man1/
sudo mandb
```

## macOS

```bash
brew install openssl curl grep fzf mpv aria2 ffmpeg yt-dlp
chmod +x nani-cli nani-engine
cp nani-cli nani-engine "$(brew --prefix)/bin/"
cp nani-cli.1 "$(brew --prefix)/share/man/man1/"
```

IINA can replace mpv:

```bash
brew install --cask iina
```

## Commands

NaniCLI additions:

```text
--history
--random
--nani-version
--nani-doctor
--nani-help
```

Full ani-cli-compatible commands:

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
--no-detach
--exit-after-play
--skip-title TITLE
-N, --nextep-countdown
-U, --update
```

Examples:

```bash
nani-cli "one piece"
nani "frieren" -q 1080p
nani-cli --dub "dragon ball"
nani-cli --history
nani-cli --random
nani-cli -d -e 1-3 "cowboy bebop"
```

## Troubleshooting

Run:

```bash
nani-cli --nani-doctor
openssl version
```

Clear stale caches after replacing an older Botan/Node build:

```bash
rm -rf ~/.cache/nani-cli ~/.cache/ani-cli
```

If Scoop keeps the old archive, run in PowerShell:

```powershell
scoop uninstall nani-cli
scoop cache rm nani-cli
scoop update
scoop install nani-cli
```

## Disclaimer

NaniCLI does not host media. Use it only with sources and content you are authorized to access.

## Credits

Based on ani-cli by pystardust, maintained and extended as NaniCLI by NavineDevs.
