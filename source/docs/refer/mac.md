title: Mac 操作 
---

## 键盘符号 KEYMAP

![mac_keymap](./mac_keymap.jpg)


## 查看端口号

```shell
netstat -atp tcp | grep -i "listen"

sudo lsof -i -P | grep -i "listen"
sudo lsof -i | grep LISTEN

netstat -ap tcp
```


## Finder 显示隐藏文件和文件夹

第一步：打开「终端」应用程序。

第二步：输入如下命令：

```shell
defaults write com.apple.finder AppleShowAllFiles -boolean true

killall Finder
```

第三步：按下「Return」键确认。

现在你将会在 Finder 窗口中看到那些隐藏的文件和文件夹了。

如果你想再次隐藏原本的隐藏文件和文件夹的话，将上述命令替换成

```shell
defaults write com.apple.finder AppleShowAllFiles -boolean false

killall Finder
```


## .DS_Store

### 禁止生成

打开 “终端” ，复制黏贴下面的命令，回车执行，重启 Mac 即可生效。

```shell
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool TRUE
```

### 恢复生成

```shell
defaults delete com.apple.desktopservices DSDontWriteNetworkStores
```

### 删除

```shell
sudo find / -name ".DS_Store" -depth -exec rm {} \;

或者

find <your path> -name ".DS_Store" -depth -exec rm {} \;
```


## 快捷键 shortcuts

本文仅列出常用的快捷键，详细请参考官网 [Mac 键盘快捷键](https://support.apple.com/zh-cn/HT201236)

`cmd-z` 撤销<br>
`cmd-shift-z` 重做<br>
`cmd-x` 拷贝<br>
`cmd-c` 拷贝<br>
`cmd-v` 粘贴<br>
`cmd-a` 全选<br>
`cmd-s` 保存<br>
`cmd-f` 查找<br>
`cmd-q` 退出<br>
`cmd-alt-esc` 强制退出应用程序<br>

`cmd-m` 最小化当前应用程序窗口<br>
`cmd-h` 隐藏当前应用程序窗口<br>
`cmd-alt-h` 隐藏其他应用程序窗口<br>

`cmd-shift-3` 截取全部屏幕<br>
`cmd-shift-4` 截取部分屏幕<br>



## 修改 hosts 文件

** hosts 文件地址

```shell
/private/etc/hosts
```

** 刷新 DNS 缓存

```shell
sudo killall -HUP mDNSResponder
```
