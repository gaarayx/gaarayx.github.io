# vim使用笔记

# 搜索相关

| 作用         | 操作                    |
| ------------ | ----------------------- |
| 快速搜索单词 | 光标移到所选单词，输入# |
|              |                         |
|              |                         |

# 问题记录

## ubuntu12如何安装vim 7.4

安装：
sudo add-apt-repository ppa:nmi/vim-snapshots
sudo apt-get update; sudo apt-get install vim

卸载还原：
sudo apt-get install ppa-purge; sudo ppa-purge ppa:nmi/vim-snapshots

## space vim

问题：
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
  
