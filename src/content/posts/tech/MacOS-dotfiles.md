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
# MacOS下的dotfiles及软件记录

::github{repo="Joyu42/dotfiles"}

## [Aerospace](https://github.com/nikitabobko/AeroSpace)-桌面窗口平铺管理工具

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

## [Karabiner-Elements](https://github.com/pqrs-org/Karabiner-Elements)-Hyper按键映射，全局vim光标移动

1. 安装

```bash 
brew install karabiner-elements
```

2. 导入配置文件\
		没啥讲的就是把caps lock映射成Hyper键（Ctrl+Alt+Shift+Cmd\
		  ps：切换输入法请自行换成shift\
		按住Hyper+H/J/K/L vim式上下左右

## [homerow](https://github.com/nchudleigh/homerow)-Vim全局跳转与滚动

1. 安装

```bash
brew install homerow
```

2. 主要就是可以自己设置快捷键实现无鼠标操作\
   个人设置：\
   				Hyper + f -> clicking（快速跳转）\
   				Hyper + s -> Scrolling（滚动）

