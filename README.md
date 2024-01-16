# Git-Tutorial

这是一个git学习仓库，用来学习git的常用命令，git最核心的功能就是分支管理、版本切换、多人合作以及大文件仓库管理。

## gitignore

用来忽略某些临时文件（比如编译产生的临时文件）

## gitattribute

Gitattributes 用于设置文件的属性。和 gitignore 类似，gitattributes 是在目录内创建 `.gitattributes` 文本文件，用于设置文件的属性，一般用于设置行尾转换、字符编码等等一系列属性。正常情况下，Git 默认的设置都能够使我们达到要求，也能够自动识别文件，不需要单独使用 gitattributes 进行指定。但是一些特殊情况下还是有必要的。在这里，我们仅对 gitattributes 做一个简短的介绍，想要深入了解的读者可以自行查阅相关资料进行学习，读者也可以跳过本部分。

> 举一个比较常见的例子。Windows 下文本文件的行尾是 CRLF（即一个字节 13 加上一个字节 10），而 Linux 下文本文件的行尾是 LF。如果无论什么系统均是逐个字节提交到 Git 仓库，则该 Git 仓库很难达到跨操作系统的目的。因此，默认情况下，Windows 平台上的 Git 会进行行尾转换，把文本文件的 CRLF 转换为 LF 提交到 Git 仓库，而把 Git 仓库调入到当前目录时则把 LF 转换回 CRLF；而 Linux 平台下则不进行行尾转换。这样以保证 Git 仓库内的文本文件文件均为 LF 行尾。但是存在一种情况，我们在一些意外情况下使得 Linux 系统上也出现了 CRLF 结尾的文件（例如 Linux 远程共享了 Windows 系统的文件夹），这样由于 Linux 系统的 Git 不进行行尾转换，便使得 Git 仓库中出现了 CRLF 行尾的文件，污染了 Git 仓库。这可以通过 `git config`，让 Linux 系统上的 Git 开启行尾转换而解决。但是，我们在多人合作开发的时候，很难要求所有人都进行设置。因此，使用 gitattributes 便可以让所有人的 Git 忽略自己的默认设置，而使用 `.gitattributes` 则可以让 Git 自动识别文本文件并进行行尾转换。
>
> Gitattributes 一般的语法为：`<filename> <attributes>`。要达到上述目的，只需要在 `.gitattributes` 中写一行
>
> ```
> * text=auto
> ```
>
> 其中，`*` 代表所有文件，`text=auto` 是让 Git 自动判断文件是二进制文件还是文本文件并进行行尾转换。



