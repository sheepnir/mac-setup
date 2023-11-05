# New MAC Setup

## Initial Cleanup and Finder Setup

cmd+space will be used for the launcher

1. Log in to iCloud
2. Open the Mac App Store and install XCode
3. Fix the Doc area to have - Finder, Safari, Settings, Terminal, and Launch Pad.
4. Finder Settings: - View -> Show Status bar - View -> Show Path Bar - View -> Show Tab Bar - View -> as List - Show hidden file by holding Shift+cmd+. - Create a new folder in the home directory, "Developer," and drag it into the Finder favorites - Arrange the favorites to your liking

## Installing Homebrew and packages

Install Xcode command line:

```
	xcode-select --install
```

Install homebrew from [brew.sh](https://brew.sh)

```
	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Run any follow-up commands

## Terminal Configuration

Download and install the Hack fonts:
https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/Hack.zip

Install Iterm2 by running

```
	brew install --cask iterm2
```

Set up the color, font (HackNerdFontMono), and font size.

Install Git

```
	brew install git
```

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

(Optional) Install powerlevel10K:

```
	brew install powerlevel10k
  echo "source $(brew --prefix)/share/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc

  # Restart zsh
  exec zsh
  p10k configure
```

## Installing Homebrew and packages

Install homebrew from [brew.sh](https://brew.sh)
Run any follow-up commands

Install:

- google chrome
- Raycast
- beyond compare
- VSCode
- 1Password
- slack
- zoom
-

```
brew install --cask google-chrome raycast visual-studio-code sublime-text 1password 1password-cli slack zoom
```
