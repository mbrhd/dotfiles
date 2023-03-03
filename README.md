# Config files to replicate env

This repo contains dotfiles for my macOS setup

Watch the [video collaboration](https://youtu.be/r_MpUP6aKiQ "Dotfiles in 100 Seconds on YouTube") between [fireship.io](https://fireship.io/ "Build and ship 🔥 your app ⚡ faster") and [eieio.xyz](http://dotfiles.eieio.xyz "Dotfiles from Start to Finish-ish"). 

## Steps to bootstrap a new Mac

1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.

```zsh
xcode-select --install
```


2. Clone repo into new hidden directory.

```zsh
# Use SSH (if set up)...
git clone git@github.com:mbrhd/dotfiles.git ~/.dotfiles

# ...or use HTTPS and switch remotes later.
git clone https://github.com/mbrhd/dotfiles.git ~/.dotfiles
```


3. Create symlinks in the Home directory to the real files in the repo.

```zsh
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/.dotfiles/.zshrc ~/.zshrc
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```


4. Install Homebrew, followed by the software listed in the Brewfile.

```zsh
# These could also be in an install script.

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
cd ~/.dotfiles && brew bundle
```

5. Configure Neovim 

After installing [NeoVim](https://github.com/neovim/neovim/wiki/Installing-Neovim) 
```
ln -s ~/.dotfiles/.config/nvim ~/.config/nvim 
```


## TODO List

- Learn how to use [`defaults`](https://macos-defaults.com/#%F0%9F%99%8B-what-s-a-defaults-command) to record and restore System Preferences and other macOS configurations.
- Organize these growing steps into multiple script files.
- Automate symlinking and run script files with a bootstrapping tool like [Dotbot](https://github.com/anishathalye/dotbot).
- Revisit the list in [`.zshrc`](.zshrc) to customize the shell.
- Make a checklist of steps to decommission your computer before wiping your hard drive.
- Create a [bootable USB installer for macOS](https://support.apple.com/en-us/HT201372).
- Integrate other cloud services into your Dotfiles process (Dropbox, Google Drive, etc.).
- Find inspiration and examples in other Dotfiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).

## Thanks

Thanks to [Jeff](https://twitter.com/jeffdelaney23 "Follow Jeff Delaney on Twitter") and  [his stage](https://fireship.page.link/youtube "Fireship YouTube Channel").
