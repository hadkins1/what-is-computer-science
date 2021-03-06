# The Linux Command Line 学习笔记

> 原版：[《The Linux Command Line》](http://linuxcommand.org/tlcl.php)
> 中译版： 《Linux 命令行大全》

## 其他总结
- [Linux Shell 相关知识点](https://github.com/ShannonChenCHN/iOSLevelingUp/issues/2#issuecomment-338358993)
- [Shell 脚本学习总结](https://github.com/ShannonChenCHN/iOSDevLevelingUp/tree/master/iOSTutorials/BashExample)

## 目录
- 第一部分 学习 shell
  - 第 1 章 shell 是什么
  - 第 2 章 文件系统导航
  - 第 3 章 Linux 系统
  - 第 4 章 操作文件和目录
  - 第 5 章 命令的使用
  - 第 6 章 重定向
  - 第 7 章 透过shell看世界
  - 第 8 章 高级键盘技巧
  - 第 9 章 权限
  - 第 10 章 进程
- 第二部分 配置和环境
  - 第 11 章 环境
  - 第 12 章 VI 编辑器
  - 第 13 章 定制提示符
- 第三部分 常见任务和主要工具
  - 第 14 章 软件包管理
  - 第 15 章 存储介质
  - 第 16 章 网络
  - 第 17 章 文件搜索
  - 第 18 章 归档和备份
  - 第 19 章 正则表达式
  - 第 20 章 文本处理
  - 第 21 章 格式化输出
  - 第 22 章 打印
  - 第 23 章 编译程序
- 第四部分 编写 shell 脚本


## 第一部分 学习 shell


### 第 1 章 shell 是什么

- shell 是一个接收键盘输入命令，并将其传递给操作系统来执行的程序。
- sh 和 bash
- 终端（terminal）
- shell 提示符：`$` 和 `#`
- 命令历史记录
- 光标移动
- 几个简单的命令
  - date：显示当前系统的时间和日期
  - cal：显示当月的日历
  - df：磁盘当前可用空间
  - free（macOS 上不支持）：内存可用空间
  - exit：结束终端会话


**延伸阅读**

- [Shell - Wikipedia](https://en.wikipedia.org/wiki/Shell_(computing))
- [Z shell - Wikipedia](https://en.wikipedia.org/wiki/Z_shell)
- [Bash - Wikipedia](https://en.wikipedia.org/wiki/Bash_(Unix_shell))

### 第 2 章 文件系统导航

- 文件系统树
- 根目录
- pwd：当前工作目录
- ls：列出目录内容
- cd：更改当前目录
  - 绝对路径
  - 相对路径
    - `.`
    - `..`
- 一些有用的快捷方式
  - `cd ~` 或者 `cd`：把主目录设为当前工作目录
  - `cd -`：把上一次的工作目录设为当前工作目录
  - `cd ~username`：把用户 username 的主目录设置为当前工作目录

### 第 3 章 Linux 系统

- `ls`：列出目录内容
  - 当前目录：`ls`
  - 指定目录：`ls /usr`
  - 多个目录：`ls ~ /usr`
  - 选项和参数
    - 格式：`command -options arguments`
    - 选项
      - 短选项：`ls -l`
      - 长选项：`ls --reverse`
      - 多个短选项串联：`ls -lt`
      - 长短选项同时使用：`ls -lt --reverse`
    - ls 命令常用选项（详见原书表 3-1）
      - `-a`
      - `-d`
      - `-F`
      - `-h`
      - `-l`
      - `-r`
      - `-S`
      - `-t`
      - `-i`：显示文件具体内容的具体索引节点
- `file`：确定文件类型
- `less`：查看文件内容
  - less 程序常见的键盘命令（详见表3-3）
- Linux 文件系统层次标准
  - 常见的 Linux 系统目录（详见表3-4）
    - `/`
    - `/bin`
    - `/boot`：macOS 上没有这个目录
    - `/dev`
    - `/etc`
    - `/home`：在 macOS 上，各个用户的主目录都在 `/Users` 下
    - `/lib`：在 macOS 上没有这个目录，核心系统程序使用的动态库都保存在 `/usr/lib` 目录下
    - `/lost+found`
    - `/media`
    - `/mnt`
    - `/opt`
    - `/proc`：macOS 上没有这个目录
    - `/sbin`
    - `/tmp`
    - `/usr`
    - `/usr/bin`
    - `/usr/lib`
    - `/usr/local`
    - `/usr/sbin`
    - `/usr/share`
    - `/usr/share/doc`
    - `/var`
    - `/var/log`
- 符号链接（又叫软链接，symlink）
  - 符号链接的使用场景（如果你安装了 mysql 的话，可以以 macOS 上的 `usr/local/mysql` 为例）


延伸阅读：
- http://chen-tao.github.io/2014/10/31/proc-on-mac-os-x/

### 第 4 章 操作文件和目录

- 通配符
  - 通配符（详见表 4-1）
    - `*`
    - `?`
    - `[characters]`
    - `[!characters]`
    - `[[:class:]]`
  - 常见字符类（详见表 4-2）
  - 通配符示例（详见表 4-3）
- mkdir：创建目录
  - `mkdir dir1`
  - `mkdir dir1 dir2 dir3`
- cp：复制文件和目录
  - cp 命令选项（详见表 4-4）
    - `-a`
    - `-i`
    - `-r`
    - `-u`
    - `-v`
  - cp 命令示例（详见表 4-5）
  	- `cp file1 file2`
  	- `cp -i file1 file2`
  	- `cp file1 file2 dir1`
 	- `cp file1 dir1`
 	- `cp -r dir1 dir2`
- mv：移除和重命名文件
  - mv 命令选项（详见表 4-6）
    - `-i`
    - `-u`
    - `-v`
  - mv 命令示例（详见表 4-7）
  	- `mv file1 file2`
  	- `mv -i file1 file2`
  	- `mv file1 file2 dir1`
 	- `mv dir1 dir2`
- rm：删除文件和目录
  - rm 选项
    - `-i`
    - `-r`
    - `-f`
    - `-v`
- ln：创建链接
  - 硬链接
    - 创建硬链接的命令：`ln file link`
    - 硬链接只能用于文件不能用于目录
  - 软链接/符号链接
    - 创建符号链接的命令：`ln -s item link`
  - 硬链接和软符号链接的区别
    - http://www.cnblogs.com/itech/archive/2009/04/10/1433052.html
    - https://www.ibm.com/developerworks/cn/linux/l-cn-hardandsymb-links/index.html

### 第 5 章 命令的使用


- 命令是什么：命令作为 shell 的输入，命令主要分为以下 4 种类型。
  - 可执行程序
  - shell 内置命令
  - shell 脚本
  - alias 命令
- `type`：显示命令的类型
  - 例如 `type cd`
- `which`：显示可执行程序的位置（which 只适用于可执行程序）
  - 例如 `which python`
- `--help`：许多可执行程序都支持 `--help` 选项
  - 例如 `pod --help`
- `man`：显示命令的帮助文档
  - 例如 `man cd`
- `apropos`：使用关键字在帮助手册列表中全局搜索可能有关联的命令
- `info`：具有跟 `man` 相似的功能
- `whatis`
- 使用 `alias` 创建别名
  - 小技巧：我们可以用分号来分隔多条命令，这样就可以将多条命令输入在一行中
    - 例如：`cd /usr; ls; cd -; exit;`
  - 创建别名：`alias name='string'`
    - 例如，执行 `alias foo='cd /usr; ls; cd -;'` 后，就可以直接使用 `foo` 命令了

### 第 6 章 重定向

#### 主要命令
- `cat`
- `sort`
- `uniq`
- `wc`
- `grep`
- `head`
- `tail`
- `tee`

#### 1. 标准输入、标准输出和标准错误
- 基本概念
- 标准输出重定向
  - 示例1：`ls -l /usr/bin > ls-output.txt`
  - 示例2：`ls -l /usr/bin >> ls-output.txt`
- 标准错误重定向
  - 示例：`ls -l /usr/bin 2> ls-error.txt`
- 将标准输出和标准错误重定向到同一个文件
  - 示例：`ls -l /bin/usr &> ls-output.txt`
- 处理不想要的输出
  - 示例：`ls -l /bin/usr 2> /dev/null`
- 标准输入重定向（详细使用可通过 `man cat` 命令查看）
  - 示例1：文件作为输入，终端的标准输出作为输出，`cat ls-output.txt`
  - 示例2：多个文件合成一个文件，`cat file1 file2 > merged_file`
  - 示例3：终端的标准输入作为输入，文件作为输出，`cat > lazy_dog.txt`

#### 2. 管道

- 介绍
  - 什么是管道？
    - 管道是 shell 的一个特性，基于这个特性，命令才具备从标准输入到读取数据，并将数据发送到标准输出的能力
  - 管道有什么用？
    - 我们可以将一个命令的输出作为另一个命令的输入
  - 示例：`ls -l /usr/bin | less`
- 过滤器
  - 什么是过滤器：将多条命令合在一起构成一个管道
  - 示例：`ls /bin /usr/bin | sort | less`
- uniq：报告或忽略文件中重复的行
  - 示例：`ls /bin /usr/bin | sort | uniq | less`
- wc：打印行数、字数和字节数
  - 示例：`wc ls-output.txt`
- grep：在文件中查找匹配文本
  - 格式：`grep pattern [file...]`
  - 示例：`ls /bin /usr/bin | sort | uniq | grep zip`
- head/tail：打印文件的开头部分/结尾部分
  - 示例1：`head -n 5 ls-output.txt`
  - 示例2：`tail -n 5 ls-output.txt`
- tee：将数据重定向到文件，同时还可以提供一份重定向数据的副本作为后续命令的 stdin
  - 示例：`ls /usr/bin | tee ls.txt | grep zip`

### 第 7 章 透过shell看世界

#### 1. 扩展
- 什么是扩展
  - 每次输入命令行按下 Enter 键时，bash 都会在执行命令之前对文本进行多重处理，这个处理过程就是扩展。
  - 比如，shell 会将命令中的通配符 `*` 解释为零个、单个或多个字符
- 路径名扩展
  - 示例：`echo /usr/*`
- 波浪线扩展
  - 示例：`echo ~`
- 算术扩展
  - 示例：`echo $(2 + 2)`
- 花括号扩展
  - 示例：`echo Front-{A,B,C}-Back`
- 参数扩展
  - 示例：`echo $USER`
  - 查看可用的变量列表：`printenv | less`
- 命令替换
  - 示例：`ls -l $(which cp)`
  - 示例：`` ls -l `which cp` ``


#### 2. 引用

- 双引号
  - 如果把文本放在双引号中，那么 shell 使用的所有特殊字符都将失去它们的特殊含义，而被看成普通字符，字符“$”、“\”，“\`”除外
- 单引号
  - 单引号可以屏蔽所有的扩展
- 转义字符

### 第 8 章 高级键盘技巧

#### 1. 编辑命令行

- 光标移动
  - `ctrl+b`: 前移一个字符(backward)
  - `ctrl+f`: 后移一个字符(forward)
  - `alt+b`: 前移一个单词（在 Mac 上是 `option+⬅️`，如果你用的是 iterm ，需要修改一下偏好设置）
  - `alt+f`: 后移一个单词（在 Mac 上是 `option+ ➡️`，如果你用的是 iterm ，需要修改一下偏好设置）
  - `ctrl+a`: 移到行首（a是首字母） 
  - `ctrl+e`: 移到行尾（end）
  - `ctrl+xx`: 行首到当前光标替换
- 修改文本（见表8-2）
- 剪切和粘贴文本

#### 2. 自动补齐

- tab 键

#### 3. 使用历史命令

- 查看历史记录
  - 示例：`history | less`
- 在历史命令中搜索
  - 示例：`history | grep /usr/bin`
- 以递增的方式搜索历史记录
  - 第一步，按下 `Ctrl+R`
  - 第二步，输入要查找的内容，此时终端会显示一条匹配结果
  - 第三步，再次按下 `Ctrl+R`，切换下一条匹配结果
  - 第四步，找到目标结果后，按下回车键

### 第 9 章 权限

#### 1. 所有者、组成员和其他用户

#### 2. 文件和目录的访问权限：读取、写入和执行

- chmod：更改文件模式
- 使用 GUI 设置文件模式
- umask：设置默认权限

#### 3. 更改身份

- su：切换用户
- sudo：让普通用户也可以使用 root 权限来执行指定的命令
- chown：更改文件所有者和所属群组
- chgrp：更改文件所属群组

#### 4. 权限的使用

#### 5. 更改用户密码

- passwd

### 第 10 章 进程


#### 10.1 进程如何工作

- ps：显示当前终端所有进程的运行情况
  - `ps x`：显示当前所有进程的运行情况
  - `ps aux`：跟 `ps x` 类似，但是显示更多的信息
- `top`：实时显示当前所有任务的资源占用情况

#### 10.2 控制进程

- 中断进程
  - 按下 `Ctrl+C` 键
- 让程序启动后在后台运行
  - 命令行中输入 `程序名 &`
- `ps`：查看当前终端会话中的所有进程
- 使进程回到前台运行
  - 使用命令：`fg %作业编号` 
- 停止（暂停）进程
  - 暂停前台进程：按下 `Ctrl+Z` 键
  - 让暂停的进程在前台恢复运行：`fg %作业编号`
  - 让已经启动的进程在后台运行：`bg %作业编号`

#### 10.3 信号

- 使用 kill 命令发送信号到进程
  - 语法格式：`kill -[singal] PID...`
  - 终止进程
    - `kill 进程id` 或者 `kill %作业编号`
  - kill 命令常用信号（见表 10-4）
- 使用 killall 命令发送信号给多个进程
  - 语法格式：`killall [-u user] [-signal] name...`

## 第二部分 配置和环境

### 第 11 章 环境

#### 11.1 环境中存储的是什么

- shell 在环境中存储了两种变量：环境变量和 shell 变量，以及编程数据（也就是别名和 shell 函数）
- 检查环境
  - printenv：显示环境变量
    - 格式：`printenv [variable]`
  - set：显示 shell 变量和环境变量，以及任何已经定义的 shell 函数
  - alias：列出所有的别名
  - 可以通过 `echo $变量名` 来打印环境变量
- 一些有趣的变量（见表 11-1）

#### 11.2 环境是如何建立的（启动文件/配置文件）

- 用户登录系统后，bash 程序就会启动并读取一系列称为启动文件的配置脚本，这些脚本定义了所有用户共享的默认环境。接下来，bash会读取更多存储在主目录下的用于定义个人环境的启动文件。这些步骤执行的确切顺序是由启动的shell会话类型决定的。
- 两种 shell 会话
  - login shell（会提示用户输入用户名密码）
    - login shell 的启动文件（见表 11-2）
      - `etc/profile`
      - `~/.bash_profile`
      - `~/.bash_login`
      - `~/.profile`
  - non-login shell（比如我们平时用的 GUI 终端）
    - non-login shell 的启动文件（见表 11-3）
      - `/etc/bash.bashrc`
      - `~/.bashrc`
- 在输入一条命令后，shell 是怎样找到这些命令的？
  - 当用户输入 ls，shell 不会搜索整个系统来寻找 `/bin/ls`，而是会搜索 PATH 变量中存储的目录列表
- export：可新增，修改或删除环境变量，供 shell 和后续执行的程序使用。

#### 11.3 修改环境（修改配置文件）

- 用户应当修改哪些文件
  - 一般来说，在PATH中添加目录，或者定义额外的环境变量，需要将这些更改放入到 `.bash_profile` 文件中，其他的改变则应录入 `.bashrc` 文件中。除非是系统管理员需要修改用户公用的默认设置，普通用户只需对主目录下的文件作出修改即可。当然用户也可以修改其他目录下的文件，比如`/etc`下的 `profile` 文件，而且很多情况会需要用户这样做，但是现在我们先保险点操作。
- 修改配置文件
- 激活我们的修改
  - 因为只有在启动 shell 会话时才会读取 `.bashrc` 等启动文件，所以对 `.bashrc` 做出的修改只
 有在关闭 shell 终端会话并重启的时候才会生效。
 - 当然也可以使用 `source ~/.bashrc` 命令强制命令 bash 重新读取 `.bashrc` 文件。

### 第 12 章 VI 简介

- 为什么要学习 vi
- VI 背景
  - vim 是 vi 的加强版
- 启动和退出 vi
  - 启动 
    - `vi`
    - `vim`
  - 退出
    - `:q`
    - `:q!`
- 编辑模式
  - insert 模式
    - `i`
  - 保存工作
    - `:w`
- 移动光标（见表 12-1）
- 基本编辑
- 查找和替换
- 编辑多个文件
- 保存并退出
  - `:wq`

### 第 13 章 定制提示符

#### 13.1 提示符的分解


- 提示符一般包含用户名、主机名和当前工作目录
- 提示符是由名为 `PS1` 的环境变量定义的
- shell 提示符中使用的转义字符（见表 13-1）

提示符示例：
```
[shanonn@macbook ~]$ 
```



#### 13.2 尝试设计提示符

- 我们可以修改环境变量 `PS1` 的值来自定义提示符的格式

#### 13.3 添加颜色

- 终端上的字符可以设置文本颜色和背景（可用的文本颜色的转义序列见表 13-2、13-3）


#### 13.4 移动光标

- 转义字符也可以用来定义光标（光标移动转义序列见表 13-4）

#### 13.5 保存提示符

- 可以将对环境变量 `PS1` 的修改保存到配置文件 `~/.bashrc`


## 第三部分 常见任务和主要工具


#### 第 14 章 软件包管理


#### 第 15 章 存储介质

- 挂载、卸载存储设备
- 创建新的文件系统
  - fdisk 命令
  - mkfs 命令
- 测试、修复文件系统
- 直接从/向设备转移数据

#### 第 16 章 网络

- 主要命令
  - ping
  - traceroute
  - netstat
  - ftp
  - lftp
  - wget
  - ssh
  - scp
  - sftp
- 相关术语
  - IP 地址
  - 主机名和域名
  - URI


#### 16.1 检查、检测网络

- ping：向网络主机发送特殊数据包
  - 示例：`ping baidu.com`
- traceroute：跟踪网络数据包的传输路径
  - 示例：`traceroute baidu.com`
- netstat：查看网络设置和相关数据
  - 示例：`netstat -r`

#### 16.2 通过网络传输文件

- ftp：采用 FTP（文本传输协议）传输文件
- lftp：更好的 ftp
- wget：用于文件下载的命令行程序，可以从网站上下载文件
  - 示例：`wget http://www.baidu.com`

#### 16.3 与远程主机的安全通信

- ssh：安全登录远程计算机
  - 示例：`ssh -T git@github.com`
  - 延伸阅读：https://help.github.com/en/articles/testing-your-ssh-connection
- scp：使用 SSH 加密隧道进行网络文件复制传输
  - 示例：`scp /Applications/Reveal.app/Contents/SharedSupport/iOS-Libraries/libReveal.dylib root@192.168.0.X:/Library/MobileSubstrate/DynamicLibraries`
  - 延伸阅读：https://www.jianshu.com/p/3d163e52c6e9
- sftp：ftp 程序的安全版本

#### 第 17 章 文件搜索


- locate：
  - 示例：`locate bin/zip`
  - 延伸阅读：https://www.cnblogs.com/devilyouwei/p/6336863.html
- find：在文件系统目录框架中查找文件
  - test 选项
  - action 选项
  - option 选项
- 其他命令
  - touch：更改文件的修改时间和打开时间，如果该文件不存在就新建一个
  - stat：显示文件或文件系统的状态


#### 第 18 章 归档和备份

- 文件压缩
  - gzip：压缩和解压缩
  - bzip2：牺牲速度以换取高质量的数据压缩
- 文件归档
  - tar：磁带归档工具
  - zip：打包和压缩文件
- 文件同步
  - rsync：远程文件和目录的同步


#### 第 19 章 正则表达式

- grep 程序
- 正则表达式的介绍和语法规则

#### 第 20 章 文本处理

- 基本操作
  - `cat`
  - `sort`
  - `uniq`
- 切片和切块
  - `cut`
  - `paste`
  - `join`
- 文本比较
  - `comm`
  - `diff`：逐行比较文件
  - `patch`：对原文件进行 diff 操作
- 非交互式文本编辑
  - `tr`
  - `sed`：用于文本过滤和转换的流编辑器
  - `aspell`



#### 第 21 章 格式化输出

- 简单的格式化工具
  - `nl`：对行进行标号
    - 示例：`ls | nl`
  - `fold`
  - `fmt`
  - `pr`
  - `printf`：起初是为 C 语言开发的
- 文档格式化系统
  - roff 和 TEX 家族
  - groff——文档格式化系统


#### 第 22 章 打印

都是跟打印相关的，可以不用看。

#### 第 23 章 编译程序

讲编译的，跟 shell 关系不大，对编译链接有所了解的话，可以不看。

## 第四部分 编写 shell 脚本

见 [Shell 脚本学习总结](https://github.com/ShannonChenCHN/iOSDevLevelingUp/tree/master/iOSTutorials/BashExample)。
