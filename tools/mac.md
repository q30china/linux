# MACOS

## LazyVim相关

### 1. github 安装nerd fonts 字体

- git拉取

```bash

git clone <https://github.com/ryanoasis/nerd-fonts.git> --depth 1
```

- 安装字体

```bash

nerd-fonts/install.sh
```

- 配置iterm2

```
Profile -> Text -> Font = “Hack Nerd Font”
```

### 2. brew 安装nerd fonts 字体和lazyvim依赖

```bash
brew search nerd-font
brew tap homebrew/cask-fonts
brew install --cask font-hack-nerd-font
brew install --cask font-fira-code-nerd-font
```

*你可以将 font-hack-nerd-font 替换为其他你喜欢的 Nerd Fonts 变种，
比如 font-fira-code-nerd-font、font-inconsolata-lgc-nerd-font 等。*

```bash
brew install jesseduffield/lazygit/lazygit
brew install ripgrep
brew install fd
```

### 3. 安装lazyvim
