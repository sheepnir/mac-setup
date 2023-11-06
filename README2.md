# My MAC Setup

This repo contains info on all the apps / tools / settings I use on my Mac machines.

## What Macbook do I have?

I am currently using the 2022 13" M2 Macbook Air as my laptop and 2023 M3 Max Macbook Pro 14" as my desktop/laptop. I also have a 2022 Macbook Pro 13" from work that I use to access sensative customer information.

These are the specs at a glance:

- Macbook Pro M3 2023
  - 14‑inch MacBook Pro - Space Black
  - Apple M3 Max chip with 14‑core CPU
  - 30‑core GPU
  - 16‑core Neural Engine
  - 36GB unified memory
  - 1TB SSD storage
- Macbook Air M2
  - 13-inch MacBook Air - Midnight Blue
  - Apple M2 chip with 8‑core CPU
  - 8‑core GPU
  - 16‑core Neural Engine
  - 8GB unified memory
  - 256GB SSD storage

## Initial Cleanup and Finder Setup

1. Log in to iCloud
2. Fix the Doc area to have - Finder, Safari, Settings, Terminal, and Launch Pad.
3. Finder Settings:
   - View -> Show Status bar
   - View -> Show Path Bar
   - View -> Show Tab Bar
   - View -> as List
   - Show hidden file by holding Shift+cmd+.
   - Create a new folder in the home directory, "Developer," and drag it into the Finder favorites
   - Arrange the favorites to your liking

## Installing Homebrew and packages

Open the Terminal and install oh-my-zsh from [ohmyszh.sh](https://ohmyz.sh/)

Istall oh-my-zsh plugins:

```
	brew install zsh-autosuggestions
```

- Change to the half-life theme and git plugin by editing ~/.zshrc file value:

```
ZSH_THEME="half-life"
plugins=(git macos web-search)
```

Install Xcode command line:

```
	xcode-select --install
```

Install homebrew from [brew.sh](https://brew.sh)

```
	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Run any follow-up commands

## Warp Terminal Configuration

Install Warp termial

```
 brew install --cask warp
```

Configure fonts, look & feel and AI. Set as the default terminal.

Install Git

```
	brew install git
```

(Optional) Install powerlevel10K:

```
	brew install powerlevel10k
  echo "source $(brew --prefix)/share/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc

  # Restart zsh
  exec zsh
  p10k configure
```

## Utilities Settings

Install first set of Apps an utilities:

```
  brew install --cask google-chrome raycast visual-studio-code sublime-text 1password 1password-cli bartender aldente betterdisplay shottr
```

Set app each application in this order:

- 1Password (set the CLI and SSH Angent)
- Google Chrome (setup as the default browser)
- Raycast (setup Raycast AI)
- VS Code
- Sublime text
- Bartender (dock organization)
- Aldente (Battery optimization)
- BetterDisplay (Disply optimization for docking)
- Shottr (Screenshut capture)

Clean homebrew by running:

```
  brew cleanup
```
