# vim使用笔记

# 参考资料

交互式学习vim：  https://www.openvim.com/
快捷键：  https://vim.rtorr.com/lang/zh_cn

# 1. 环境配置

## 1.1 secureCRT

secureCRT的ubuntu配色方案：
https://blog.csdn.net/lurebreast/article/details/107670902

## 1.2 vim安装

### ubuntu12如何安装vim 7.4

安装：
sudo add-apt-repository ppa:nmi/vim-snapshots
sudo apt-get update; sudo apt-get install vim

卸载还原：
sudo apt-get install ppa-purge; sudo ppa-purge ppa:nmi/vim-snapshots

## 1.3 space vim

### 1.3.1 遇到的问题

#### 问题1：
```
slp@SLP:github$ vim
Error detected while processing function SpaceVim#begin..SpaceVim#default#options:
line   70:
E739: Cannot create directory: /home/slp/.cache//SpaceVim/
Error detected while processing function SpaceVim#end..SpaceVim#plugins#load..<SNR>44_load_plugins:
line   18:
E108: No such variable: "g:_spacevim_plugin_layer"
Press ENTER or type command to continue
```

#### 问题2：

输入vim后，报错：
```
startify: Can't read viminfo file. Read :help startify-faq-02
Error detected while processing function SpaceVim#welcome..startify#insane_in_the_membrane..<SNR>166_show_lists..<SNR>166_show_dir..<SNR>166_display_by_path..<SNR>166_filter_oldfiles:
line    6:
E714: List required
```
原因：~/.viminfo文件因所有者为root，非当前账号。
修复方案：用chown和chgrp将文件所有者改为本账号。

输入vim后，报错：
```
Error detected while processing function SpaceVim#welcome..neobundle#autoload#_command..vimfiler#init#_command..vimfiler#init#_start..<SNR>171_create_vimfiler_buffer..vimfiler#handler#_event_handler..<SNR>197
_on_BufReadCmd..vimfiler#init#_vimfiler_directory..vimfiler#view#_force_redraw_all_vimfiler..vimfiler#view#_force_redraw_screen..<SNR>183_writefile:
line    3:
E482: Can't create file /home/slp/.cache/vimfiler//files/=+home=+slp=+
Press ENTER or type command to continue
Error detected while processing function SpaceVim#welcome:
line   19:
E171: Missing :endif
```
原因：同上，/home/slp/.cache/vimfiler文件夹的所有者为root。
修复方案：同上。

# 2. 快捷键

| 作用         | 操作                    |
| ------------ | ----------------------- |
| 快速搜索单词 | 光标移到所选单词，输入*/#（向下/向上） |
|              |                         |
|              |                         |

## 2.1分屏操作
### 进入vim前分屏
水平分屏：
vim -o[n] file1 [file2...]
垂直分屏：
vim -O[n] file1 [file2...]

### 进入vim后分屏
水平分屏：
:sv [file]
垂直分屏：
:vs [file]

### 新建子屏

ctrl+w n 新建文件，并以水平子屏出现

### 光标在子屏间移动
ctrl+w  w/p/h/j/k/l（w/p表示下个/上个分屏，h/j/k/l表示左/上/下/右）

### 子屏的移动
ctrl+w  H/J/K/L（H/J/K/L表示左/上/下/右）

### 子屏的尺寸控制
ctrl+w -/+ 减少/增加当前窗口高度（仅上下分屏）
ctrl+w >/< 减少/增加当前窗口宽度（仅左右分屏）
ctrl+w = 使所有窗口恢复均等

### 关闭子屏
ctrl+w c/q/o
c: 关闭当前子屏
q: 关闭当前子屏，若为最后一个，则退出vim
o: 仅保留当前子屏

# 3. 插件

## 3.1 vim-plug

安装：
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

配置插件：
修改vim配置文件：
```
call plug#begin('~/.vim/plugged')
Plug 'XXX/XXX' (Note: plugin git repo name)
call plug#end()
```

命令：
```
:PlugStatus    #检查状态
:PlugInstall    #安装配置文件的插件
:PlugUpdate    #更新插件
:PlugDiff    #查看插件更新内容(在每个段落上按x可将插件回滚)
:PlugClean    #删除插件（注释掉vim配置文件中的插件后，执行该命令）
:PlugUpgrade    #升级vim-plug本身
```
