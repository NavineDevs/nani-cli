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
- nani -h
- nani-cli -h
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

#### Install dependencies
```bash
brew install curl grep aria2 ffmpeg git fzf yt-dlp
brew install --cask iina
```

#### Install NaniCLI
```bash
git clone https://github.com/NavineDevs/nani-cli.git
cd nani-cli
chmod +x nani-cli
cp nani-cli "$(brew --prefix)"/bin/
cp nani-cli.1 "$(brew --prefix)"/share/man/man1/
```

Test:
```bash
nani-cli
man nani-cli
```

---

### 🪟 Windows (Scoop)

### you need gitbash install using powershell or gitbash website https://git-scm.com/install/windows

#### Install Scoop (PowerShell)
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
iwr -useb get.scoop.sh | iex
```

### Install git using scoop (powershell)
``` 
scoop install git
```

### command line for powershell profile
```
%USERPROFILE%\scoop\apps\git\current\bin\sh.exe -i -l
```

### Install extras
```
scoop bucket add extras
scoop install extras/windows-terminal
scoop install extras/vlc
```
### Install Dependencies
```
scoop install fzf ffmpeg mpv yt-dlp
```

#### Add bucket & install
```powershell
scoop bucket add nani-cli https://github.com/NavineDevs/nani-cli
scoop install nani-cli
```

Test:
```powershell
nani-cli
```

> 💡 For best results on Windows, use **Windows Terminal + Git Bash**.

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
- Downloaded Path `C:\Users\user\anime.mp4`
```To check download path (windows)
pwd
```

```Set new path(windows)
setx NANI_CLI_DOWNLOAD_DIR "$HOME\Downloads\anime
or setx NANI_CLI_DOWNLOAD_DIR "$HOME\Downloads\
```
you can change the Downloads to like Videos and anime to like movies restart the terminal after

---

## Extra stuff
```Windows install syncplay for nani-cli -s
scoop install syncplay
scoop install extras/vcredist202
```
```to unistall extras/vcredist202 
do scoop unistall extras/vcredist202
```
```Linx syncplay
sudo apt update
sudo apt install syncplay
```
```Macos syncplay
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install --cask syncplay
```
---

## ⚠️ Disclaimer

NaniCLI does not host content.  
It streams from publicly available sources.

---

## ❤️ Credits

Based on **ani-cli**, maintained and extended by **NavineDevs**.
