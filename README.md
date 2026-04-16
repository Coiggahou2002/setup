# Mac Setup

My personal macOS setup guide — a step-by-step checklist for bootstrapping a new Mac from scratch.

## Overview

| Category | Tools |
|---------|-------|
| Network | ClashV-Ninja |
| Dev Essentials | Xcode, Homebrew, Git, gh |
| Browser | Chrome |
| Terminal | iTerm2, oh-my-zsh, Powerlevel10k |
| Fonts | Iosevka, Monaspace |
| Editor | VSCode |
| AI | Claude Code |
| Productivity | Raycast, Karabiner-Elements, Maccy, Typeless |
| Peripherals | Mac Mouse Fix |

---

# Setup Checklist

## 1. 安装 ClashV-Ninja

[jinkela.app](jinkela.app)

## 2. 安装 Xcode

App Store 搜索 Xcode 安装，或终端执行：

```bash
xcode-select --install
```

## 3. 安装 Homebrew

> 需要先完成 XCode Command Line Tools 的安装，才能安装 homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 4. 安装 Chrome

> 本步骤需依赖 Clash-V-Ninjia，因为需要fq🪜

下载安装：https://www.google.com/chrome/

## 5. 安装依赖 homebrew 的软件

```bash
# 终端字体
brew install --cask font-iosevka

# 代码字体
brew install --cask font-monaspace

# 剪贴板历史 
brew install --cask maccy

# GitHub CLI
brew install gh
```

## 6. 安装 iTerm2

下载安装：https://iterm2.com/downloads.html

## 7. 通过 Raycast + Karabiner-Elements 定制应用拉起的快捷键

- 安装 [Raycast](https://www.raycast.com/)
- 安装 [Karabiner-Elements](https://karabiner-elements.pqrs.org)
- 完成后修改 Caps Lock 键映射为 Ctrl+Shift+Alt+Cmd
- 配置 Raycast 快捷键
    - [ ] Caps + H → Chrome
    - [ ] Caps + V → VSCode
    - [ ] Caps + L → Lark

## 8. VSCode

1. 安装 [VSCode](https://code.visualstudio.com/)
2. 通过 GitHub 登陆，Sync Settings
3. 安装 vim 插件
4. 安装 Markdown Preview GitHub 插件

## 9. 安装 Typeless

下载安装：https://typeless.app/

## 10. 安装 Claude Code

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

## 11. 让 Claude Code 安装 oh-my-zsh

## 12. 设置 ~/zshrc

```
alias pull="git pull"
alias gco="git checkout"

alias proxy="export https_proxy=http://127.0.0.1:6789 http_proxy=http://127.0.0.1:6789 all_proxy=socks5://127.0.0.1:6789 && echo '✅ proxy configured in current session'"
alias claudep="claude --dangerously-skip-permissions"

alias zshconf="vim ~/.zshrc"
alias reloadzsh="source ~/.zshrc"
```

## 13. Mac Mouse Fix

安装 [Mac Mouse Fix](https://macmousefix.com/)

用来 revert 鼠标滚轮