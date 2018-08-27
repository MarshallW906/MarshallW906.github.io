# Mac下golang的配置

## 安装方式
主要有2种安装方式，一种是HomeBrew(`brew install go`)，一种是直接用官网的pkg包安装。

安装的过程很简单，这里不再赘述。下面说一下对go的配置，以及一些必要包的安装方式。两种方法虽然安装的位置不同，但后面配置的过程是一样的。

## 配置环境变量
go的环境变量配置，，主要与2个文件夹有关：`$GOPATH`和`$GOROOT`。
`$GOROOT`是go的安装目录，`$GOPATH`是go的“当前用户目录”，存放当前用户的**go代码**，由**go代码生成的可执行文件**，以及**下载的包(packages)**。设置好这两个目录即可。

首先，安装完之后，确认go的安装。这里`go env`很有用。可以显示go的**推荐配置**，包括path的设置，一些编译开关等等。
如果安装成功的话，输入`go env`，可以看到一系列变量设置。在`go env`之后加上某个条目的名字，如`go env GOPATH`，即可单独显示该条目，利用这一点，我们可以方便的修改配置。

首先在用户根目录(`~/`)下，创建go文件夹，用作`$GOPATH`。
```bash
mkdir -p $GOPATH
```

然后编辑`.bashrc`（zsh用户编辑`.zshrc`），在末尾添加如下。

```bash
# Golang
export GOPATH=$(go env GOPATH)
export GOROOT=$(go env GOROOT)
export PATH=$PATH:$(go env GOPATH)/bin
```
保存之后重新开启shell即可。

## 依赖包的安装

依赖包的安装需要用到`go get`和`go install`两个命令。顾名思义，前者是下载和安装（可通过参数指定只下载不安装），后者则是将已有的代码包编译成可执行文件，并加入到`$GOPATH/bin`下。（在mac下是如此，在win和linux中可能是加入到`$GOROOT/bin`下，未确认）

这里强烈建议先用`go get`下载，再用`go install`安装。

下面是一些go get常用的辅助参数。个人常用`go get -u -v`。

`-insecure` 允许非安全下载，主要是针对没有HTTPS的HTTP路径。
`-u` 这个很常见，有更新的话会覆盖本地的package，默认不会覆盖的。
`-v` 显示Log，即verbose.
`-t` 同时下载需要运行测试的package.
`-d` 只下载，但不安装package.

## 其他
写代码用什么工具这个问题。。。推荐Visual Studio Code[\(点我传送\)](https://code.visualstudio.com/download)。安装go插件即可。
IDE的话，intelliJ家有go的IDE，可以一用。[点我传送](https://www.jetbrains.com/go/)
