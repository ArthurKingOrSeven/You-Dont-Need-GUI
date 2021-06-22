# 你不需要 GUI

[![加入 Spectrum 社区](https://withspectrum.github.io/badge/badge.svg)](https://spectrum.chat/you-dont-need/GUI)

<details>
It's for noobs :)
</details>
<br />

图形用户界面对计算机用户非常友好。引入它们是为了应对命令行界面 (CLI) 的陡峭学习曲线。

![Xerox Star 8010 工作站](./Xerox_Star_8010_workstations.jpg)

但是，它们通常需要更多资源，功能较弱且难以通过脚本实现自动化。

作为计算机专家，我们希望提高效率并更好地完成工作。我们知道命令词可能不容易被发现或助记，因此我们尝试列出一些您可能想在 GUI 中执行的常见任务。

## 快速链接

1. [复制文件](#copy-a-file)
1. [复制文件](#duplicate-a-file)
1. [复制目录](#copy-a-directory)
1. [复制目录](#duplicate-a-directory)
1. [移动文件](#move-a-file)
1. [重命名文件](#rename-a-file)
1. [移动目录](#move-a-directory)
1. [重命名目录](#rename-a-directory)
1. [合并目录](#merge-directories)
1. [创建一个新文件](#create-a-new-file)
1. [新建目录](#create-a-new-directory)
1. [显示文件/目录大小](#show-filedirectory-size)
1. [显示文件/目录信息](#show-filedirectory-info)
1. [用默认程序打开文](#open-a-file-with-the-default-program)
1. [压缩一个目录](#zip-a-directory)
1. [解压目录](#unzip-a-directory)
1. [查看压缩文件中的文件](#peek-files-in-a-zip-file)
1. [删除文件](#remove-a-file)
1. [删除目录](#remove-a-directory)
1. [列出目录内容](#list-directory-contents)
1. [树视图目录及其子目录](#tree-view-a-directory-and-its-subdirectories)
1. [查找陈旧文件](#find-a-stale-file)
1. [显示日历](#show-a-calendar)
1. [寻找未来的日期](#find-a-future-date)
1. [使用计算器](#use-a-calculator)
1. [强制退出程序](#force-quit-a-program)
1. [检查服务器响应](#check-server-response)
1. [查看文件内容](#view-content-of-a-file)
1. [搜索文本](#search-for-a-text)
1. [查看图片](#view-an-image)
1. [显示磁盘大小](#show-disk-size)
1. [检查计算机性能](#check-performance-of-your-computer)
1. [快速提示](#quick-tips)
1. [热键](#hotkeys)
1. [我不记得这些神秘命令](#i-cant-remember-these-cryptic-commands)


## copy a file

**停止拖放文件，或 CMD/CTRL + C、CMD/CTRL + VA 文件** :-1:

复制 `readme.txt` 到 `documents` 目录

```shell
$ cp readme.txt documents/
```

## duplicate a file

**停止右键单击并复制文件** :-1:

```shell
$ cp readme.txt readme.bak.txt
```
更先进:
```shell
$ cp readme{,.bak}.txt
#注意：了解 {} 如何与 touch foo{1,2,3}.txt 一起执行，看看会发生什么。
```

## copy a directory

**停止拖放目录，或 CMD/CTRL + C、CMD/CTRL + VA 目录** :-1:

复制 `myMusic` 目录到 `myMedia` 目录

```shell
$ cp -a myMusic myMedia/
# or
$ cp -a myMusic/ myMedia/myMusic/
```

## duplicate a directory

**停止右键单击并复制目录** :-1:

```shell
$ cp -a myMusic/ myMedia/
# 或者如果 `myMedia` 文件夹不存在
$ cp -a myMusic myMedia/
```

## move a file

**停止拖放文件，或 CMD/CTRL + X、CMD/CTRL + VA 文件** :-1:

```shell
$ mv readme.txt documents/
```

**出于这个原因** 移动文件时始终使用尾部斜杠, [for this reason](http://unix.stackexchange.com/a/50533).

## rename a file

**停止右键单击并重命名文件** :-1:

```shell
$ mv readme.txt README.md
```

## move a directory

**停止拖放目录，或 CMD/CTRL + X、CMD/CTRL + VA 目录** :-1:

```shell
$ mv myMedia myMusic/
# or
$ mv myMedia/ myMusic/myMedia
```

## rename a directory

**停止右键单击并重命名目录** :-1:

```shell
$ mv myMedia/ myMusic/
```

## merge directories

**停止拖放合并目录** :-1:

```shell
$ rsync -a /images/ /images2/	# 注意：可能会覆盖同名文件，所以要小心！
```

## create a new file

**停止右键单击并创建新文件** :-1:

```shell
$ touch 'new file'    # 如果文件已经存在，则更新文件的访问和修改时间戳
# or
$ > 'new file'        # 注意：如果内容已经存在，则擦除内容
```

## create a new directory

**停止右键单击并创建新目录** :-1:

```shell
$ mkdir 'untitled folder'
# or
$ mkdir -p 'path/may/not/exist/untitled\ folder'
```

## show file/directory size

**停止右键单击并显示文件/目录信息** :-1:

```shell
$ du -sh node_modules/
```

## show file/directory info

**停止右键单击并显示文件/目录信息** :-1:

```shell
$ stat -x readme.md   # on macOS
$ stat readme.md      # on Linux
```

## open a file with the default program

**停止双击文件** :-1:

```shell
$ xdg-open file   # on Linux
$ open file       # on MacOS
```

## zip a directory

**停止右键单击并压缩目录** :-1:

```shell
$ zip -r archive_name.zip folder_to_compress
```

## unzip a directory

**停止右键单击并解压缩目录** :-1:

```shell
$ unzip archive_name.zip
```

## peek files in a zip file

**停止使用 WinRAR** :-1:

```shell
$ zipinfo archive_name.zip
# or
$ unzip -l archive_name.zip
```

## remove a file

**停止右键单击并永久删除文件** :-1:

```shell
$ rm my_useless_file
```

重要： rm 命令永久删除 my_useless_file，这相当于将 my_useless_file 移动到回收站并点击清空回收站。

## remove a directory

**停止右键单击并永久删除目录** :-1:

```shell
$ rm -r my_useless_folder
```

## list directory contents

**停止打开您的查找器或文件浏览器** :-1:

```shell
$ ls my_folder        # Simple
$ ls -la my_folder    # -l: 以列表格式显示。-a：显示所有文件，包括隐藏文件。-la 结合了这些选项.
$ ls -alrth my_folder # -r: 反向输出。-t：按时间排序（修改）。-h：输出人类可读的大小.
```

## tree view a directory and its subdirectories

**停止打开您的查找器或文件浏览器** :-1:

```shell
$ tree                                                        # on Linux
$ find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'      # on MacOS
# 注意：安装 homebrew (https://brew.sh) 以便能够使用（某些）Linux 实用程序，例如 tree。
# brew 安装树
```

## find a stale file

**停止使用您的文件浏览器查找文件** :-1:

查找 5 天前修改的所有文件

```shell
$ find my_folder -mtime +5
```

## show a calendar

**停止通过日历小部件查看本月的样子** :-1:

显示文本日历

```shell
$ cal
```

显示选定的月历和年历

```shell
$ cal 11 2018
```

## find a future date

**停止使用网络应用程序计算未来日期** :-1:

今天几号？

```shell
$ date +%m/%d/%Y
```

一周后呢？

```shell
$ date -d "+7 days"                                           # on Linux
$ date -j -v+7d                                               # on MacOS
```

## use a calculator

**停止使用计算器小部件** :-1:

```shell
$ bc
```

## force quit a program

**停止 CTRL + ALT + DELETE 并选择要杀死的程序** :-1:

```shell
$ killall program_name
```

## check server response

**停止打开浏览器** :-1:

```shell
curl -i umair.surge.sh
#  curl 的 -i (--include) 选项在其输出中包含 HTTP 响应标头。
```

## view content of a file

**停止双击文件** :-1:

```shell
$ cat apps/settings.py
# 如果文件太大而无法放在一页上，您可以使用“pager”（较少）一次显示一页。
$ less apps/settings.py
```

## search for a text

**在目录中停止 CMD/CTRL + F** :-1:

```shell
$ grep -i "Query" file.txt
```

![grep](./grep.jpg)

## view an image

**停止使用预览** :-1:

```shell
$ imgcat image.png
# 注意：需要 iTerm2 终端.
```

## show disk size

**停止右键单击磁盘图标或打开磁盘实用程序** :-1:

```shell
$ df -h
```

## check performance of your computer

**停止打开您的活动监视器或任务管理器** :-1:

```shell
$ top
```

## Quick tips

![CLI tips](./cli_tips.jpg)

## Hotkeys

```
Ctrl + A 转到您当前正在键入的行的开头
Ctrl + E 转到您当前正在输入的行的末尾
Ctrl + L 清除屏幕，类似于 clear 命令
Ctrl + U 清除光标位置之前的行。 如果您在行尾，则清除整行。
Ctrl + H 与退格键相同
Ctrl + R 让您搜索以前使用过的命令
Ctrl + C 杀死正在运行的任何东西
Ctrl + D 退出当前shell
Ctrl + Z 将您正在运行的任何内容放入暂停的后台进程。 fg 恢复它。
Ctrl + W 删除光标前的单词
Ctrl + K 清除光标后的行
Ctrl + T 交换光标前的最后两个字符
Esc + T 交换光标前的最后两个单词
Alt + F 在当前行将光标向前移动一个词
Alt + B 在当前行将光标向后移动一个词
Tab 自动完成文件和目录名称
```

## I can't remember these cryptic commands

您可以随时 google 或man您不熟悉的命令。或者, checkout [tldr](https://github.com/tldr-pages/tldr), 一组简化的和社区驱动的手册页。
