# macOS Setup

My personal guide for setting up a developer environment on macOS.

## Pre-requisites

### Xcode developer tools

Open terminal, run `xcode-select --install`.

## SSH setup

Create an SSH key using

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Run following to add SSH private keys to ssh-agent and store passphrase in keychain.

```
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

Add following to `~/.ssh/config` to automatically load keys and add keys to keychain.

```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

Finally, add the SSH key to GitHub (and/or whatever other remote repo service I use), via their web UIs.

## Terminal

### Install iTerm2

Install from [iterm2.com](https://iterm2.com/).

### Homebrew

Install using instructions at [brew.sh](brew.sh).

### Zsh and Oh My Zsh

Zsh.


```
brew install zsh
chsh -s $(which zsh)
```

Oh My Zsh.

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

I use theme `spaceship`, which also needs to be installed.

For theme configuration, plugins, etc, see my dotfile [.zshrc.macos](.zshrc.macos).

Also, following plugins need manual install:

  - `zsh-autosuggestions`
  - `zsh-syntax-highlighting`

### Terminal tools

Further tools to install:

  - Fzf, and `silversearcher-ag`, for fast searches.
  - `eza`: better `ls`.
  - `batcat`: better `cat`.
  - GitHub shell completions.

See [.zshrc.macos](.zshrc.macos) files for some aliases and exemplary setup.

## Editors / IDEs

VSCode is the go-to. We could try something new too, like [Zed](zed.dev).

## Productivity

### Stuff to try

  - Recast: Amped up spotlight replacement.
  - Obsidian: Notes.
  - Maccy: clipboard history.
  - Mole (`mo`): CLI tool with system monitors, app uninstaller, and more.
  - AppCleaner: App for deep uninstalls.

## More stuff to add.

  - Python setup, via pyenv.
  - Node/Javascript setup, via nvm.
  - Go setup.
  - Better vim setup.
  - Better iTerm setup, especially colours.
  - Claude Code.
