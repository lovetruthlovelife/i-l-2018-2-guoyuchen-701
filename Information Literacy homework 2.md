﻿# 第一次作业:git与github区别
## git
Git(读音为/gɪt/)是一个开源的分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理。 Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。
git是一个版本管理工具，是可以在你电脑不联网的情况下，只在本地使用的一个版本管理工具，其作用就是可以让你更好的管理你的程序，比如你原来提交过的内容，以后虽然修改了，但是通过git这个工具，可以把你原来提交的内容重现出来，这样对于你后来才意识到的一些错误的更改，可以进行还原。
## github
gitHub是一个面向开源及私有软件目的托管平台，因为只支持git 作为唯一的版本库格式进行托管，故名gitHub。
每个程序员自己写的程序，可以在github上建立一个网上的仓库，你每次提交的时候可以把代码提交到网上，这样你的每次提交，别人也都可以看到你的代码，同时别人也可以帮你修改你的代码，这种开源的方式非常方便程序员之间的交流和学习。
## git和github的作用
Git和Github托管自己的代码和读书笔记,只要有网就可以把自己的东西拷贝下来继续使用。linux下主要是托管代码用，在windows下主要是托管笔记使用的，比如一些PDF.

# 第二次作业:解释框图含义
## 工作区
工作区：工作区就是你克隆项目到本地后，项目所在的文件夹目录。我们会想当然的认为，当前仓库所在目录就是我们的工作区，其实这是不完全正确的。在当前仓库中，新增，更改，删除文件这些动作，都发生在工作区里面。
## 暂存区
暂存区：英文叫stage, 或index。用于存储工作区中添加上来的变更（新增、修改、删除）的文件的地方。操作时，使用git add .会将本地所有新增、变更、删除过的文件的情况存入暂存区中。
在版本库.git）目录下，有一个index文件。它实际上就是一个包含文件索引的目录树，像是一个虚拟的工作区。在这个虚拟工作区的目录树中，记录了文件名、文件的状态信息（时间戳、文件长度等），文件的内容并不存储其中，而是保存在Git对象库（.git/objects）中，文件索引建立了文件和对象库中对象实体之间的对应。如果当前仓库，有文件更新，并且使用git add 命令，那么这些更新就会出现在暂存区中。
## 本地仓库
本地仓库：用于存储本地工作区和暂存区提交上来的变更（新增、修改、删除）过的文件的地方。操作时，使用git commit –m “本次操作描述” 可以将添加到暂存区的修改的文件提交到本地仓库中。
## 远程仓库
远程仓库：简单来说，就是我们工作过程中，当某一个人的开发工作完毕时，需要将自己开发的功能合并到主项目中去，但因为功能是多人开发，如果不能妥善保管好主项目中存储的代码及文件的话，将会存在丢失等情况出现，所以不能将主项目放到某一个人的本地电脑上，这时就需要有一个地方存储主项目，这个地方就是我们搭建在服务器上的git远程仓库，也就是在功能开始开发前，每个人要下载项目到本地的地方。操作时，使用git push origin 分支名称，将本次仓库存储的当前分支的修改推送至远程仓库中的对应分支中。

## 工作区、暂存区、本地仓库、远程仓库的关系：
我们如果想将在本地工作区中修改，推送到远程仓库的话，需要将工作区的修改的内容，添加到暂存区，再将暂存区的内容提交到本地仓库，最终将本地仓库的内容推送至远程仓库，才能达到最终想要将本地修改推送到远程仓库的目的。

如果想在远程仓库中修改，同步到工作区的话，需要更新和merge到暂存区，暂存区commit到本地仓库，本地仓库push到远程仓库。
