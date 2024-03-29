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

Install Xcode command line:

```
	xcode-select --install
```

Install homebrew from [brew.sh](https://brew.sh)

```
	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Run any follow-up commands

Install oh-my-zsh plugins:

```
	brew install zsh-autosuggestions
```

- Change to the half-life theme and git plugin by editing ~/.zshrc file value:

```
ZSH_THEME="half-life"
plugins=(git macos web-search)
```

## Warp Terminal Configuration

Install Warp termial

```
 brew install --cask warp
```

Configure fonts, look & feel and AI. Set as the default terminal.

**Setup permissions** under Settings -> Privacy Security -> App Management

(Optional) Install powerlevel10K:

```
	brew install powerlevel10k
  echo "source $(brew --prefix)/share/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc

  # Restart zsh
  exec zsh
  p10k configure
```

## Utilities Settings

Privacy: install Proton VPN

```
  brew install --cask protonvpn
```

Login to your account and connect to the fastest node.

Install first set of Apps an utilities:

```
  brew install --cask google-chrome raycast visual-studio-code sublime-text 1password 1password-cli bartender aldente betterdisplay shottr rectangle grammarly
```

Set app each application in this order:

- 1Password (set the CLI and SSH Angent)
- Google Chrome (setup as the default browser)
  - Extensions:
    - [1Password Nightly](https://chrome.google.com/webstore/detail/1password-nightly-%E2%80%93-passw/gejiddohjgogedgjnonbofjigllpkmbf?hl=en)
    - [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm?hl=en)
    - [Grammarly](https://chrome.google.com/webstore/detail/grammarly-grammar-checker/kbfnbcaeplbcioakkpcpgfkobkghlhen?hl=en)
- Raycast (setup Raycast AI)
- Rectangle (screen organizer)
- VS Code
- Sublime text
- Bartender (dock organization)
- Aldente (Battery optimization)
- BetterDisplay (Disply optimization for docking)
- Shottr (Screenshut capture)
- Grammarly (spell and grammar checker)

Clean homebrew by running:

```
  brew autoremove && brew cleanup -s && rm -rf "$(brew --cache)"
  brew doctor && brew missing
```

## Development environment setup on VM with Ubuntu Linux

Download Ubuntu arm64.iso file from:
https://cdimage.ubuntu.com/jammy/daily-live/current/

Update Homebrew:

```
  brew update && brew upgrade && brew upgrade --greedy
  brew autoremove && brew cleanup -s && rm -rf "$(brew --cache)"
  brew doctor && brew missing
```

Install UTM virtualization:

```
  brew install --cask utm
```

### Setup Ubuntu VM

Add the ISO file to UTM and un-check "Use Apple Virtualization"

In the Ubuntu install:

1. Select Normal Installation, Download Updates, and Install 3rd Party...
2. Select "Erase disk and install Ubuntu" option
3. Choose simple user and password and set to "Log in automatically"

After the install open the terminal and run:

```
  sudo apt install spice-vdagent spice-webdavd
  gsettings set org.gnome.desktop.background picture-uri ''
  gsettings set org.gnome.desktop.background primary-color 'rgb(66, 81, 100)'
```

Shut down the VM and close the window. On the settings, select sharing and change "Directory Share Mode" to "WebDAV". Reboot the VM. Click Shared folder and confirm location. Open Files in Ubuntu and click "Other Locations" -> "Spice Client".

Run the following privacy settings in the terminal:

```
  sudo apt purge -y apport apport-symptoms popularity-contest ubuntu-report whoopsie

  sudo apt autoremove -y
```

### Set development environment

Install Git

```
  sudo apt install git
```

Update Python:

```
  sudo add-apt-repository ppa:deadsnakes/ppa

  sudo apt update

  sudo apt install python3.11 # or any version

  echo "alias python='python3.11'" >> ~/.bashrc

  source ~/.bashrc

```

Install VSCode:
https://code.visualstudio.com/docs/setup/linux#_rhel-fedora-and-centos-based-distributions

## Development environment setup (local)

### Setup Git

Install Git

```
	brew install git gh
```

Configure git with your name/email:

```
git config --global user.name user_name
git config --global user.email email
git config --global core.editor vim
```

In the termial, go to ~/Developer:

```
gh repo clone sheepnir/mac-setup
```

setup the authentication.

### Python setup

Installation

```
  brew install python
```

(optional) Add alias to the .zprofile file:

```
  echo "alias python=python3" >> ~/.zprofile
  echo "alias pip=pip3" >> ~/.zprofile
```

### Useful utilities

Install the followings:

```
  brew install ffmpeg yt-dlp youtube-dl
```
