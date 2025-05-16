# 💻 MERN Stack Development Environment Setup for macOS (M3 Max 2023)

This guide sets up a professional developer environment for full-stack JavaScript (MERN Stack) 
development using tools and configurations suited for macOS.

---

## 🧰 Tools & Stack Overview

| Category         | Tools / Stack                       |
|------------------|-------------------------------------|
| Shell & Terminal | zsh, Oh My Zsh, iTerm2, Warp        |
| Code Editor      | VS Code, Neovim                     |
| Version Control  | Git, GitHub CLI                     |
| Programming      | Node.js, React.js, Express.js, Java |
| Database         | MongoDB, MongoDB Compass            |
| Web Tools        | HTML, CSS, Postman, Browsers        |
| Productivity     | Raycast, Rectangle, Onyx            |
| Cloud            | AWS CLI, Heroku CLI                 |

---

#!/bin/bash

echo "Starting MERN dev environment (Terminal Emulator) setup..."


# Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"


# Terminals & Shells
brew install --cask iterm2 warp
brew install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"


# Fonts and themes
brew tap homebrew/cask-fonts
brew install --cask font-hack-nerd-font
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git \
  ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k


# ZSH plugins
brew install zsh-autosuggestions zsh-syntax-highlighting


# Editors
brew install --cask visual-studio-code
brew install sublim
brew install neovim


# Git and GitHub CLI
brew install git gh
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main

# Node.js
brew install nvm
mkdir ~/.nvm
export NVM_DIR="$HOME/.nvm"
source $(brew --prefix nvm)/nvm.sh
nvm install --lts
nvm use --lts
brew install yarn

# MongoDB
brew tap mongodb/brew
brew install mongodb-community@7.0
brew services start mongodb/brew/mongodb-community
brew install --cask mongodb-compass

# Browsers and tools
brew install --cask google-chrome brave-browser postman

# Cloud
brew install awscli
brew tap heroku/brew && brew install heroku

# Productivity
brew install --cask raycast rectangle onyx 




$echo "✅ MERN Stack dev environment setup complete!"

