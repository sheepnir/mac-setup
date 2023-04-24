# Mac Setup

This repo contains info on all the apps / tools / settings I use on my Mac mchines.

## What Macbook do I have?

I am currently using the 2020 13" M1 Macbook Pro as my laptop and 2022 M1 Max Mac Studio as my desktop.

These are the specs at a glance:

- Macbook Pro Laptop
  - Apple M1
    - 8-Core CPU
    - 8-Core GPU
  - 8GB RAM
  - 256GB SSD
- Mac Studio Laptop
  - Apple M1 Max
    - 10-Core CPU
    - 24-Core GPU
    - 16-Core Neural Engine
  - 32GB RAM
  - 512GB SSD

Read more about these Macs [Macbook Pro 2020 M1](https://everymac.com/systems/apple/macbook_pro/specs/macbook-pro-m1-8-core-13-2020-specs.html) , [Mac Studio 2022 M1 Max](https://everymac.com/systems/apple/mac-studio/specs/mac-studio-m1-max-10-core-cpu-24-core-gpu-2022-specs.html#macspecs1)

## Step 1 - Homebrew / oh my zsh / Terminal

### Homebrew

[Homebrew](https://brew.sh/) is my preferred package management solution. It allows to install tools and apps from the command line.

To install it, open up the built in `Terminal` app and run this command:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This will also install the xcode build tools which is needed by many other developer tools.

After Homebrew is done installing, use it to install everything else.

### oh-my-zsh

To customize the termial I use [$ oh my zsh](https://ohmyz.sh/) and run:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

I use the half-life theme and git plugin by editing ~/.zshrc file value:

```sh
ZSH_THEME="half-life"
plugins=(git macos)
```

See more info about the [macos](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/macos) plugin

My `.zshrc` is on [github here](https://github.com/) so I can copy it over to any machine.

Copy this file (or create your own) in your home directory:

```sh
cd ~
curl -O https://github.com
```

### Terminal

I use the Mac OS terminal as my default. I use the Homebrew profile and change the font size to 14, the font collor to RGB (0,255,0), and the backgrond color to 50% opacity and 5% blur.
All settings are saved to a binary file that is located at:

```sh
~/Library/Preferences/
com.apple.Terminal.plist
```

My setting file, com.apple.Terminal.plist, is available [here](https://github.com/sheepnir/mac-setup/tree/main/MacSettingFiles). Download and save to ~/Library/Preferences/

### Configure and install Chrome, 1Password, and Sublime Text

Run:

```sh
brew install --cask google-chrome
brew install --cask 1password
brew install --cask sublime-text
```

### Configure Git

I use brew to install the latest version of `git`:

```sh
git --version
brew install git
```

Open a new tab / window to start using the latest version:

```sh
git --version
```

Configure git with your name / email and preferred editor:

```sh
git config --global user.name w3cj
git config --global user.email cj@null.computer
git config --global core.editor nano
```

#### Other command line tools I use

- [ffmpeg](https://en.wikipedia.org/wiki/FFmpeg) - edit videos from the command line
- [imagemagick](https://en.wikipedia.org/wiki/ImageMagick) - edit images from the command line

```sh
brew install ffmpeg
brew install imagemagick
```

## Development Tools

### Python

Install using brew:

```sh
brew install python
```

To see it is running from /opt/homebrew/bin/python3, run:

```sh
type python3
echo $PATH # To see that the brew path is first in the queue
```

(Optional) Add alias to the .zprofile file:

```sh
alias python=python3
alias pip=pip3
```

Open pyton and run `import sys`, `sys.execuable` to ensure that it points to the brew installation location

### XCode

Download and install from the Mac apps store

### Node.js and npm

Run:

```sh
brew install node
```

### Github

Go to github.com to creare a personal access token
Intall github cli running:

```sh
brew install gh
```

See more info [here](https://cli.github.com/)

## OS Productivity

### Window Management

I use [rectangle](https://rectangleapp.com/) to move and resize windows using keyboard shortcuts.

It is highly recommend installing this and memorizing the keyboard shortcuts.

```sh
brew install rectangle
```

### AltTab - App Switching

I use an app switcher called [AltTab](https://alt-tab-macos.netlify.app/). It shows full window previews, and has an option to show a preview for every open window in all applications (even minimized ones).

I replace the built-in `CMD+TAB` shortcut with AltTab.

```sh
brew install alt-tab
```

### Raycast - Quick Launching

The built in spotlight search is a bit slow for me and usually has web search results as the default instead of apps or folders on my machine.

I use [Raycast](https://www.raycast.com/) to launch apps / folders.

```sh
brew install --cask raycast
```

## Other Apps I Use Daily

Copy the file 'my_brew_packages.txt' to the home directory, then run:

```sh
xargs brew install < my_brew_packages.txt
```

## OS Settings

These are my preferred settings for `Finder` and the `Dock`.

### Finder

- Finder -> Preferences
  - General -> Show these on the desktop -> Select None
    - I try to keep my desktop completely clean.
  - General -> New Finder windows show -> Home Folder
    - I prefer to see my home folder in each new finder window instead of recent documents
  - Advanced -> Show all filename extensions -> Yes
  - Advanced -> Show warning before changing an extension -> No
  - Advanced -> When performing a search -> Search the current folder
- View

  - Show Status Bar
  - Show Path Bar
  - Show Tab Bar

  See link to the config file [here](https://github.com/sheepnir/mac-setup/tree/main/MacSettingFiles)

## Menu Bar Customization

### Menu Bar Calendar

I like to have a calendar in the menu bar that I can quickly look at. stats does not include one, so I found [itsycal](https://www.mowglii.com/itsycal/). It seems fine for my needs.

```sh
brew install itsycal
```

itsycal shows the date, so I hide the date in the system menu bar widget:

- System Preferences
  - Dock & Menu Bar
    - Clock
      - Show Date -> Never
      - Show Day of Week -> No

## Note Taking

There are likely a million other better options, but I have used [Sublime Text](https://www.sublimetext.com/) as a note taking app for years now. I essentially use it as a staging area before moving my notes into a more permanent place (Google Docs, Google Keep, Trello, actual code project READMES etc.) or I delete the note (close the tab) after it has served its purpose.

I use sublime because it allows me to open new tabs / files without the need to save a given file. I can have several tabs / staging areas open and then completely close sublime. When I open it back up, all of my tabs are still there.

## VS Code

VS Code is my preferred code editor.

You can view all of my VS Code settings / extensions [here](https://github.com/sheepnir/mac-setup/tree/main/VSCodeSettings).
