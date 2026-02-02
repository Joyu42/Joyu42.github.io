---
title: MacOS-dotfiles
published: 2026-02-01T15:16:22.232Z
description: ''
updated: ''
tags:
  - tech
  - mac
  - unix
draft: false
pin: 0
toc: true
lang: ''
abbrlink: ''
---
# MacOS下的一些dotfiles及软件分享
(部分配置文件可在以下仓库中找到)
::github{repo="Joyu42/dotfiles"}
## [homebrew](https://github.com/Homebrew/brew)-软件包管理器
伟大无须多言
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
## [iTerm2](https://github.com/gnachman/iTerm2)-经典好用终端
```bash
brew install iterm2
```
1. 壁纸
   ![](src/content/posts/_images/iShot_2026-02-02_21.19.48.png)
   ![](src/content/posts/_images/iShot_2026-02-02_21.22.40.png)
2. 字体(下载好后在终端设置里启用即可)
   ```bash
   brew insatll font-maple-mono-nf-cn
   ```
## [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev)-科学且明智地使用互联网
```bash
brew install clash-verge-rev
```
配置文件请自行[寻找]((https://verge.dginv.click/#/register?code=oaxsAGo6))
## [oh-my-zsh] + [starship]-shell插件与美化
[(详细oh-my-zsh配置参考)](https://www.haoyep.com/posts/zsh-config-oh-my-zsh/)
1. 设置默认终端为zsh（<mark>注意：不要使用sudo</mark>）
   ```bash
   chsh -s /bin/zsh
   ```
2. 安装oh-my-zsh
   ```bash
   # via curl
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   # via curl(国内镜像)
   sh -c "$(curl -fsSL https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"
   # via wget
   sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
   # via wget(国内镜像)
   sh -c "$(curl -fsSL https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"
3. 安装插件\
   plugins=(
   git 
   brew 
   z 
   extract 
   you-should-use
   zsh-syntax-highlighting 
   zsh-autosuggestions
   )
   1. git(内置)
   2. 

## [raycast](https://www.raycast.com/)-强大可扩展的快速启动器
1. 关闭系统自带聚焦，"cmd + space" 快捷键启动raycast
2. 设置quicklinks,以及Alias，快速调出搜索
   ![_](src/content/posts/_images/iShot_2026-02-02_20.15.34.png)
3. 设置favorites
   ![_](src/content/posts/_images/iShot_2026-02-02_20.18.44.png)

## [aerospace](https://github.com/nikitabobko/AeroSpace)-桌面窗口平铺管理工具

[官方文档](https://nikitabobko.github.io/AeroSpace/guide#normalization)

1. 安装

``` bash
brew install --cask nikitabobko/tap/aerospace
```

2. 配置文件讲解

   1. 搭配[borders](https://github.com/FelixKratz/JankyBorders)使用（对当前激活窗口边框高亮）

    ``` toml
   after-startup-command = ['exec-and-forget borders active_color=0xffe1e3e4 inactive_color=0xff494d64 width=5.0 hidpi=true style=round']
    ```

   2. 删除F工作区（与Karabiner-Elements快捷键冲突）

   ```toml
      persistent-workspaces = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "A", "B","C", "D", "E","F"（删除）,"G", "I", "M", "N", "O", "P", "Q","R", "S", "T", "U", "V", "W", "X", "Y", "Z"]
   ```
   ~~alt-f = 'workspace F'~~\
   ~~alt-shift-f = 'move-node-to-workspace F'~~

   3. 调整边距

   ```toml
    inner.horizontal = 10
    inner.vertical =   10
    outer.left =       10
    outer.bottom =     10
    outer.top =        10
    outer.right =      10
   ```

   4. 添加全屏快捷键

   ```toml
   alt-f = 'fullscreen'
   ```

   5. 手风琴"alt+,",平铺"alt+/"
   6. 系统（临时启动）应用默认用floating，即不服从aerospace管理

   ```toml
   # 访达 Finder
   [[on-window-detected]]
   if.app-id = 'com.apple.finder'
   run = 'layout floating'
   ```

   可用以下命令查看应用id

   ```bash
   osascript -e 'id of app "finder"'
   ```

   7. 多屏幕使用时强制分配工作区给显示器

   ```toml
   [workspace-to-monitor-force-assignment]
   	C = 'dell'   #代码       
    Q = 'dell'   #qq微信
    7 = 'dell'    
    8 = 'dell'    
    9 = 'dell'    
    M = 'built-in'       # 工作区 M 留给笔记本自带屏##
   ```

## [karabiner-elements](https://github.com/pqrs-org/Karabiner-Elements)-Hyper按键映射，全局vim光标移动

1. 安装

```bash 
brew install karabiner-elements
```

2. 导入配置文件\
		主要做的就是把caps lock映射成Hyper键（Ctrl+Alt+Shift+Cmd）\
		  ps：切换输入法请自行换成shift\
		按住Hyper+H/J/K/L vim式上下左右
   ![_](src/content/posts/_images/iShot_2026-02-02_20.20.01.png)
## [homerow](https://github.com/nchudleigh/homerow)-vim式全局跳转与滚动

1. 安装

```bash
brew install homerow
```

2. 主要就是可以自己设置快捷键实现无鼠标操作\
   个人设置：\
   ![_](src/content/posts/_images/iShot_2026-02-02_20.26.58.png)
   ![_](src/content/posts/_images/iShot_2026-02-02_21.07.40.png)
