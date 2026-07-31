# 🎬 NaniCLI

A fast and simple CLI tool to browse, watch, and download anime from the terminal.  
**Fully compatible with ani-cli**, with extra quality-of-life features.

<p align="center">
  <img src="https://img.shields.io/badge/os-linux-brightgreen">
  <img src="https://img.shields.io/badge/os-macos-brightgreen">
  <img src="https://img.shields.io/badge/os-windows-yellowgreen">
</p>

---

## ✨ Features & alias: nani

- `nani -h`
- `nani-cli -h`
- Watch anime from the terminal
- Download episodes (`-d`)
- Resume watching (`--continue`)
- Watch history (`--history`)
- Random anime (`--random`)
- Uses `mpv`, `iina`, or `vlc`

---

## 📦 Installation

### 🐧 Linux (Debian / Ubuntu)

```bash
sudo apt update
sudo apt install -y curl grep aria2 ffmpeg git fzf yt-dlp mpv

git clone https://github.com/NavineDevs/nani-cli.git
cd nani-cli
chmod +x nani-cli
sudo cp nani-cli /usr/local/bin/
sudo cp nani-cli.1 /usr/local/share/man/man1/
sudo mandb
```

Test:

```bash
nani-cli
```

---

### 🍎 macOS

```bash
brew install curl grep aria2 ffmpeg git fzf yt-dlp
brew install --cask iina

git clone https://github.com/NavineDevs/nani-cli.git
cd nani-cli
chmod +x nani-cli
cp nani-cli "$(brew --prefix)"/bin/
cp nani-cli.1 "$(brew --prefix)"/share/man/man1/
```

---

### 🪟 Windows (Git Bash)

Install Git for Windows:
https://git-scm.com/install/windows

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
iwr -useb get.scoop.sh | iex
scoop install git
scoop bucket add extras
scoop install windows-terminal vlc fzf ffmpeg mpv yt-dlp
```

Use Git Bash and run:

```bash
nani-cli
```

---

## ▶️ Usage

```bash
nani-cli
nani
nani-cli -d
nani-cli --continue
nani-cli --history
nani-cli --random
```

---

## 📁 Files

- Config: `~/.config/nani-cli/config`
- History: `~/.config/nani-cli/history.json`
- Cache: `~/.cache/nani-cli/`

---

## 📄 Help

```bash
nani-cli --help
```

Set download directory (Windows):

```powershell
setx NANI_CLI_DOWNLOAD_DIR "%USERPROFILE%\\Downloads\\anime"
```

Restart the terminal after changing the environment variable.

---

## Extra

### Windows

```powershell
scoop install syncplay
scoop install extras/vcredist2022
```

### Linux

```bash
sudo apt install syncplay
```

### macOS

```bash
brew install --cask syncplay
```

---

## ⚠️ Disclaimer

NaniCLI does not host content.
It streams from publicly available sources.

---

## ❤️ Credits

Based on **ani-cli**, maintained and extended by **NavineDevs**.
