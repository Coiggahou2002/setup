# Mac Setup

My personal macOS setup guide — a step-by-step checklist for bootstrapping a new Mac from scratch.

## Overview

| Category | Tools |
|---------|-------|
| Network | ClashV-Ninja |
| Dev Essentials | Xcode, Homebrew, Git, gh, fnm, Node.js |
| Browser | Chrome |
| Terminal | iTerm2, oh-my-zsh, Powerlevel10k |
| Fonts | Iosevka, Monaspace |
| Editor | VSCode |
| AI | Claude Code |
| Productivity | Raycast, Karabiner-Elements, Maccy, Typeless, Snipaste |
| Peripherals | Mac Mouse Fix |

---

# Setup Checklist

## 1. Install ClashV-Ninja

[jinkela.app](jinkela.app)

## 2. Install Xcode

Install from App Store, or run in terminal:

```bash
xcode-select --install
```

## 3. Install Homebrew

> Xcode Command Line Tools must be installed first.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 4. Install Chrome

> Requires ClashV-Ninja (proxy) to be set up first in 🇨🇳.

Download: https://www.google.com/chrome/

## 5. Install Homebrew packages

```bash
# Terminal font
brew install --cask font-iosevka

# Code font
brew install --cask font-monaspace

# Clipboard manager
brew install --cask maccy
```

## 6. Install GitHub CLI and sign in

```bash
brew install gh
gh auth login
```

## 7. Configure Git

```bash
git config --global user.name "your-username"
git config --global user.email "your-email@example.com"
```

## 8. Install fnm and Node.js

> Tools like Claude Code depend on Node.js. Use [fnm](https://github.com/Schniz/fnm) (Fast Node Manager) to manage versions.

```bash
brew install fnm
```

Add to `~/.zshrc`:

```bash
eval "$(fnm env --use-on-cd --shell zsh)"
```

Then install Node.js:

```bash
fnm install --lts
fnm default lts-latest
```

## 9. Install iTerm2

Download: https://iterm2.com/downloads.html

## 10. Set up app-switching shortcuts with Raycast + Karabiner-Elements

- Install [Raycast](https://www.raycast.com/)
- Install [Karabiner-Elements](https://karabiner-elements.pqrs.org)
- Remap Caps Lock to Hyper Key (Ctrl+Shift+Alt+Cmd)
- Configure Raycast hotkeys:
    - [ ] Caps + H → Chrome
    - [ ] Caps + V → VSCode
    - [ ] Caps + L → Lark

## 11. VSCode

1. Install [VSCode](https://code.visualstudio.com/)
2. Sign in with GitHub to sync settings
3. Install Vim extension
4. Install Markdown Preview GitHub extension

## 12. Install Typeless

Download: https://typeless.app/

## 13. Install Claude Code

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

## 14. Install oh-my-zsh via Claude Code

## 15. Configure ~/.zshrc

```bash
alias pull="git pull"
alias gco="git checkout"

alias proxy="export https_proxy=http://127.0.0.1:6789 http_proxy=http://127.0.0.1:6789 all_proxy=socks5://127.0.0.1:6789 && echo '✅ proxy configured in current session'"
alias claudep="claude --dangerously-skip-permissions"

alias zshconf="vim ~/.zshrc"
alias reloadzsh="source ~/.zshrc"
```

## 16. Enable key repeat on long press

```bash
defaults write -g ApplePressAndHoldEnabled -bool false
```

> By default macOS shows an accent picker on long press. This disables it so keys repeat instead (useful for Vim).

## 17. Install Snipaste

Install [Snipaste](https://www.snipaste.com/)

## 18. Mac Mouse Fix

Install [Mac Mouse Fix](https://macmousefix.com/)

Used to reverse mouse scroll direction.
