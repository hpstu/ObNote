# 引言

## 用户信息

安装完 Git 之后，要做的第一件事就是设置你的用户名和邮件地址。 这一点很重要，因为每一个 Git 提交都会使
用这些信息，它们会写入到你的每一次提交中，不可更改：

```sh
git config --global user.name "hp"
git config --global user.email 571091694@qq.com
```

再次强调，如果使用了 --global 选项，那么该命令只需要运行一次，因为之后无论你在该系统上做任何事情， Git 都会使用那些信息。 当你想针对特定项目使用不同的用户名称与邮件地址时，可以在那个项目目录下运行没有 `--global` 选项的命令来配置。

很多 GUI 工具都会在第一次运行时帮助你配置这些信息。

## 文本编辑器

既然用户信息已经设置完毕，你可以配置默认文本编辑器了，当 Git 需要你输入信息时会调用它。 如果未配置，Git 会使用操作系统默认的文本编辑器。

如果你想使用不同的文本编辑器，例如 Emacs，可以这样做：

```sh
git config --global core.editor emacs
```

在 Windows 系统上，如果你想要使用别的文本编辑器，那么必须指定可执行文件的完整路径。 

## 检查配置信息

如果想要检查你的配置，可以使用 `git config --list` 命令来列出所有 Git 当时能找到的配置。

你可能会看到重复的变量名，因为 Git 会从不同的文件中读取同一个配置（例如：/etc/gitconfig 与~/.gitconfig）。 这种情况下，Git 会使用它找到的每一个变量的最后一个配置。

你可以通过输入` git config <key>`： 来检查 Git 的某一项配置:

```sh
git config user.name
# hpstu
```

```sh
git config user.email
# 571091694@qq.com
```

由于Git会从多个文件中读取同一配置变量的不同值，因此你可能会在其中看到意料之外的值而不知道为什么。此时，你可以查询Git中该变量的原始值，它会告诉你哪一个配置文件最后设置了该值：

```sh
git config --show-origin user.name
# file:C:/Users/hp/.gitconfig     hpstu
```

## 获取帮助

```
git xxx -h
```

# Git基础

## 获取Git仓库

通常有两种获取 Git 项目仓库的方式：

1. 将尚未进行版本控制的本地目录转换为 Git 仓库；

2. 从其它服务器 克隆 一个已存在的 Git 仓库。

两种方式都会在你的本地机器上得到一个工作就绪的 Git 仓库。

### 在已存在目录中初始

```sh
cd /home/user/my_project
```

之后执行：

```sh
git init
```

## 克隆现有的仓库

当你执行 git clone 命令的时候，默认配置下远程 Git 仓库中的每一个文件的每一个版本都将被拉取下来。

克隆仓库的命令是 git clone <url> 。 比如，要克隆 Git 的链接库 libgit2，可以用下面的命令：

```sh
git clone https://github.com/libgit2/libgit2
```

如果你想在克隆远程仓库的时候，自定义本地仓库的名字，你可以通过额外的参数指定新的目录名：

```sh
git clone https://github.com/libgit2/libgit2 mylibgit
```

这会执行与上一条命令相同的操作，但目标目录名变为了 mylibgit。

Git 支持多种数据传输协议。 上面的例子使用的是 https:// 协议，不过你也可以使用 git:// 协议或者使用SSH 传输协议，比如 user@server:path/to/repo.git 。



















