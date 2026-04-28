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
| AI | Claude Code, Ollama |
| Productivity | Raycast, Karabiner-Elements, Maccy, Typeless, Snipaste |
| Peripherals | Mac Mouse Fix |

---

# Setup Checklist

## 1. Climb Out of the GFW

Install ClashV-Ninja: [jinkela.app](jinkela.app)

## 2. Get Apple's Dev Toolchain

Install Xcode from App Store, or run in terminal:

```bash
xcode-select --install
```

## 3. Get Package Manager

Install Homebrew:

> Xcode Command Line Tools must be installed first.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 4. Get a Real Browser

Install Chrome:

> Requires ClashV-Ninja (proxy) to be set up first in 🇨🇳.

Download: https://www.google.com/chrome/

## 5. Install Fonts

> Fonts for coding and terminal.

```bash
# Terminal font
brew install --cask font-iosevka

# Code font
brew install --cask font-monaspace
```

## 6. Get a Clipboard History Manager

```bash
# Clipboard manager
brew install --cask maccy
```

## 7. Authenticate with GitHub CLI

```bash
brew install gh
gh auth login
```

## 8. Set Git Identity

```bash
git config --global user.name "your-username"
git config --global user.email "your-email@example.com"
```

## 9. Set Up Node.js Version Management

Install fnm and Node.js:

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

## 10. Get a Better Terminal

Install iTerm2: https://iterm2.com/downloads.html

Then install Shell Integration (enables inline image display in terminal):

```bash
curl -L https://iterm2.com/shell_integration/install_shell_integration_and_utilities.sh | bash
```

> **Note:** iTerm2 is the best terminal overall, but it has some rendering issues when used with Coding CLIs like Claude Code. If you are a heavy Claude Code user, consider using [Kaku](https://github.com/tw93/kaku) instead.

## 11. Switch Apps Without Touching the Trackpad

Set up app-switching shortcuts with Raycast + Karabiner-Elements:

- Install [Raycast](https://www.raycast.com/)
- Install [Karabiner-Elements](https://karabiner-elements.pqrs.org)
- Remap Caps Lock to Hyper Key (Ctrl+Shift+Alt+Cmd)
- Configure Raycast hotkeys:
    - [ ] Caps + H → Chrome
    - [ ] Caps + V → VSCode
    - [ ] Caps + L → Lark
    - [ ] Caps + O → Obsidian
    - [ ] Caps + S → Superhuman
    - [ ] Caps + M → Outlook
    - [ ] ...

## 12. Get Code Editor

Install VSCode:

1. Install [VSCode](https://code.visualstudio.com/)
2. Sign in with GitHub to sync settings
3. Install Vim extension
4. Install Markdown Preview GitHub extension

## 13. Stop Typing Repetitive Text

Install [Typeless](https://typeless.app/)

## 14. Get Your AI Coding Partner

Install Claude Code:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

## 15. Make the Shell Usable

Installing and configuring oh-my-zsh (with plugins, themes, etc.) is a bit tedious. Just let Claude Code handle it — ask it to install and set up oh-my-zsh for you.

## 16. Set Up Shell Aliases

Configure `~/.zshrc`:

```bash
alias pull="git pull"
alias gco="git checkout"

alias proxy="export https_proxy=http://127.0.0.1:6789 http_proxy=http://127.0.0.1:6789 all_proxy=socks5://127.0.0.1:6789 && echo '✅ proxy configured in current session'"
alias claudep="claude --dangerously-skip-permissions"

alias zshconf="vim ~/.zshrc"
alias reloadzsh="source ~/.zshrc"
```

## 17. Fix Long-Press Behavior for Vim

Enable key repeat on long press:

```bash
defaults write -g ApplePressAndHoldEnabled -bool false
```

> By default macOS shows an accent picker on long press. This disables it so keys repeat instead (useful for Vim).

## 18. Screenshot and Pin Anything

Install [Snipaste](https://www.snipaste.com/)

## 19. Run LLMs Locally

Install [Ollama](https://ollama.com/):

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

## 20. Fix Mouse Scroll Direction

Install [Mac Mouse Fix](https://macmousefix.com/)

macOS only lets you pick one scroll direction for everything. Mac Mouse Fix decouples the two: trackpad keeps its natural scroll direction, while the mouse wheel is reversed to match physical expectations.

## 21. Use F-Keys Without Holding Fn

In **System Settings → Keyboard**, enable **"Use F1, F2, etc. keys as standard function keys"**.

By default, bare F-key presses trigger media controls (brightness, volume); you need Fn+F1 to send a real function key. Flipping this setting reverses the behavior — F1 sends a real function key directly, and Fn+F1 triggers media controls instead.
