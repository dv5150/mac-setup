# macOS setup

## Steps

1. **Install macOS & system updates**

2. **Set up your own favorite system settings**

3. **Set app switcher to show on all displays**
     ```bash
     defaults write com.apple.Dock appswitcher-all-displays -bool true; killall Dock
     ```

4. **Install Homebrew**
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

5. **Install Software with Homebrew**
    - Copy line 1 for full terminal setup
    - Copy line 2 for work setup
    - Copy line 3 for other software
    - Copy line 4 for Proton software
     ```bash
     brew install --cask ghostty font-meslo-lg-nerd-font && brew install starship zoxide eza zsh-autosuggestions zsh-syntax-highlighting && \
     brew install --cask herd docker-desktop phpstorm hoppscotch mattermost github && brew install git && \
     brew install --cask firefox spotify shottr maccy linearmouse dropshelf keepassxc yubico-authenticator pearcleaner && \
     brew install --cask proton-pass proton-drive proton-mail protonvpn standard-notes
     ```

6. **Copy this into your ~/.zshrc file**
    ```
    if [ -f ~/.zshrc_main ]; then
        . ~/.zshrc_main
    fi

    if [ -f ~/.work_aliases ]; then
        . ~/.work_aliases
    fi
    ```

7. **Clone this repo and copy the dotfiles and config files to `~/` and `~/.config/` respectively**
    
8. **Open ~/.zshrc_main and remove all the lines for software you're not using**