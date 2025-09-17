# macOS setup

- **Install macOS & system updates**

- **Set up your own favorite system settings**

- **Configure Finder to always open in list view**

    - Open finder
    - `Cmd` + `J`
    - Check the top two check boxes (Always open in list view, browse in list view)
    - Click "Use as Defaults"
    - `sudo find / -name ".DS_Store"  -exec rm {} \;`

- **Set app switcher to show on all displays**
     ```bash
     defaults write com.apple.Dock appswitcher-all-displays -bool true; killall Dock
     ```

- **Install Homebrew**
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

- **Install Software with Homebrew**
    - Copy line 1 for full terminal setup
    - Copy line 2 for work setup
    - Copy line 3 for other software
    - Copy line 4 for Proton software
     ```bash
     brew install --cask ghostty font-jetbrains-mono-nerd-font && brew install starship zoxide eza bat zsh-autosuggestions zsh-syntax-highlighting && \
     brew install --cask herd sequel-ace docker-desktop phpstorm coteditor hoppscotch mattermost github && brew install git && \
     brew install --cask brave-browser spotify shottr maccy linearmouse keepassxc yubico-authenticator pearcleaner && \
     brew install --cask proton-pass proton-drive proton-mail protonvpn standard-notes
     ```

- **Copy this into your ~/.zshrc file**
    ```
    if [ -f ~/.zshrc_main ]; then
        . ~/.zshrc_main
    fi

    if [ -f ~/.work_aliases ]; then
        . ~/.work_aliases
    fi
    ```

- **Clone this repo and copy the dotfiles and config files to `~/` and `~/.config/` respectively**

- **Open ~/.zshrc_main and remove all the lines for software you're not using**

- **Make [Home], [End], [Page Up] and [Page Down] keys behave like on Windows**

    ```bash
    mkdir ~/Library/KeyBindings/
    ```

    ```bash
    touch ~/Library/KeyBindings/DefaultKeyBinding.dict
    ```

    Copy:
    ```
    {
        "\UF729"  = moveToBeginningOfLine:;
        "\UF72B"  = moveToEndOfLine:;
        "$\UF729" = moveToBeginningOfLineAndModifySelection:;
        "$\UF72B" = moveToEndOfLineAndModifySelection:;
        "\UF72C" = pageUp:;
        "\UF72D" = pageDown:;
        "$\UF72C" = pageUpAndModifySelection:;
        "$\UF72D" = pageDownAndModifySelection:;
    }
    ```