# vim使用笔记

# 1. 环境配置

## 1.1 secureCRT

secureCRT的ubuntu配色方案：
https://blog.csdn.net/lurebreast/article/details/107670902

## vim安装

### 1.2 ubuntu12如何安装vim 7.4

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


# 2. 快捷键

| 作用         | 操作                    |
| ------------ | ----------------------- |
| 快速搜索单词 | 光标移到所选单词，输入# |
|              |                         |
|              |                         |
