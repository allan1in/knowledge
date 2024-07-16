- [1 介绍](#1-介绍)
  - [版本控制](#版本控制)
  - [Git 的特点](#git-的特点)
- [2 Git 基础](#2-git-基础)
  - [安装 Git](#安装-git)
    - [安装](#安装)
    - [配置](#配置)
    - [中文乱码](#中文乱码)
  - [获取 Git 仓库](#获取-git-仓库)
    - [本地仓库](#本地仓库)
    - [远程仓库](#远程仓库)
  - [基础操作](#基础操作)
    - [检查状态](#检查状态)
    - [跟踪](#跟踪)
    - [暂存](#暂存)
    - [.gitignore](#gitignore)
    - [比较](#比较)
    - [提交](#提交)
    - [合并提交](#合并提交)
    - [删除文件](#删除文件)
    - [移动文件](#移动文件)
    - [贮藏工作区](#贮藏工作区)
    - [提交日志](#提交日志)
    - [撤销](#撤销)
    - [版本回退](#版本回退)
    - [远程仓库](#远程仓库-1)
    - [打标签](#打标签)
    - [别名](#别名)
- [3 Git 分支](#3-git-分支)
  - [分支简介](#分支简介)
    - [暂存做了什么？](#暂存做了什么)
    - [提交做了什么？](#提交做了什么)
    - [什么是分支？](#什么是分支)
    - [创建分支做了什么？](#创建分支做了什么)
    - [如何确定当前分支？](#如何确定当前分支)
    - [切换分支做了什么？](#切换分支做了什么)
    - [合并分支做了什么？](#合并分支做了什么)
  - [分支开发工作流](#分支开发工作流)
    - [长期分支](#长期分支)
    - [主题分支](#主题分支)
  - [远程分支](#远程分支)
    - [远程分支？远程跟踪分支？跟踪分支？](#远程分支远程跟踪分支跟踪分支)
    - [如何区分本地分支和远程跟踪分支？](#如何区分本地分支和远程跟踪分支)
    - [将远程仓库 clone 到本地会创建分支吗？](#将远程仓库-clone-到本地会创建分支吗)
    - [远程分支有新的内容怎么办？](#远程分支有新的内容怎么办)
    - [可以有多个远程跟踪分支吗？](#可以有多个远程跟踪分支吗)
    - [如何推送自己的分支？](#如何推送自己的分支)
    - [跟踪分支都是自动创建的吗？](#跟踪分支都是自动创建的吗)
  - [变基](#变基)
  - [相关命令](#相关命令)
    - [查看分支](#查看分支)
    - [创建分支](#创建分支)
    - [切换分支](#切换分支)
    - [合并分支](#合并分支)
    - [删除分支](#删除分支)
    - [远程分支](#远程分支-1)
    - [变基](#变基-1)
- [4 分布式 Git](#4-分布式-git)
  - [分布式工作流程](#分布式工作流程)
    - [集中式工作流](#集中式工作流)
    - [集成管理者工作流](#集成管理者工作流)
    - [主管与副主管工作流](#主管与副主管工作流)
- [5 Github](#5-github)
  - [本地 Git 连接 Github 远程仓库](#本地-git-连接-github-远程仓库)

# 1 介绍

## 版本控制

版本控制是一种记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统

- 本地版本控制系统
- 集中化的版本控制系统（Centralized Version Control Systems，简称 CVCS）
- 分布式版本控制系统（Distributed Version Control System，简称 DVCS）（git）

分布式有利于多人协作，且数据备份不易丢失

## Git 的特点

- 直接记录快照，而非差异比较
- 操作几乎都是本地运行
- 保证数据完整性（SHA 1 校验和）
- 一般只添加数据，数据不易丢失
- 文件的三个状态（ committed 、 modified 、 staged ）对应三个区域（ Git 目录 、 工作区 、 暂存区 ）

# 2 Git 基础
## 安装 Git

### 安装

打开 cmd，输入命令查看是否安装git

```
$ Git
The program 'Git' is currently not installed. You can install it by typing:
sudo apt-get install Git
```

[下载windows版本](https://Git-scm.com/download/win)，一路默认安装

### 配置

Git 三种操作工具 

- Git Bash（ UNIX 命令 ）（***推荐***）
- Git CMD（ v2.19.1 Git CMD在Windows版本中已弃用。默认是在PATH中有Git .exe，所以CMD和Git CMD之间没有明显的区别 ）
- Git GUI（ 图形界面 ）

建议使用 Git bash，输入命令配置用户名和邮箱

- `$ Git config --global user.name "John Doe"`，配置用户名
- `$ Git config --global user.email johndoe@example.com`，配置邮箱
- `$ git config --global <configname> <configvalue>`，修改 config 的值
- `$ git config --global <configname>`，查看某个 config 的值
- `$ $ git config --list`，查看所有 config 的值

### 中文乱码

- git bash 终端输入命令：`git config --global core.quotepath false`
- 在 it bash 的界面中右击空白处，弹出菜单，选择 Options->Text->Locale 改为 zh_CN ， Character set 改为 UTF-8

## 获取 Git 仓库

### 本地仓库

1. 进入本地空目录 `$ cd /d/git-repository`
2. git 初始化 `$ git init`
3. 追踪文件（这部分文件被纳入版本控制） `$ git add README.md`
4. 提交 `$ git commit`

### 远程仓库

`$ git clone https://github.com/libgit2/libgit2 aliasname`，克隆远程仓库到本地当前目录下

## 基础操作

### 检查状态

`$ git status`，检查暂存区当前状态（有没有未暂存的修改），也可以在合并冲突时用于检查冲突文件

### 跟踪

对于工作区的新文件，Git 将其纳入追踪，并放入暂存区

`$ git add file_name`

### 暂存

对于工作区修改后的文件，将其转移到暂存区，等待被提交

`$ git add file_name`

### .gitignore

一个仓库可能只根目录下有一个 .gitignore 文件，它 ***递归*** 地应用到整个仓库中。子目录下也可以有额外的 .gitignore 文件。子目录中的 .gitignore 文件中的规则只作用于它所在的目录中。

文件 .gitignore 的格式规范:

- 所有空行或者以 # 开头的行（注释）都会被 Git 忽略
- 可以使用标准的 ***glob 模式*** 匹配，它会递归地应用在整个工作区中
- 以（/）开头防止递归（只在当前目录下匹配要忽略的文件）
- 以（/）结尾指定目录（忽略整个文件夹）
- 要忽略指定模式以外的文件或目录，可以在模式前加上叹号（!）取反

所谓的 ***glob 模式*** 是指 shell 所使用的简化了的正则表达式

- 星号（\*）匹配零个或多个任意字符
- \[abc] 匹配任何一个列在方括号中的字符 （这个例子要么匹配一个 a，要么匹配一个 b，要么匹配一个 c）
- 问号（?）只匹配一个任意字符
- 如果在方括号中使用短划线分隔两个字符， 表示所有在这两个字符范围内的都可以匹配（比如 \[0-9] 表示匹配所有 0 到 9 的数字）
- 使用两个星号（\*\*）表示匹配任意中间目录，比如 a/\*\*/z 可以匹配 a/z 、 a/b/z 或 a/b/c/z 等

.gitignore 文件的例子：

```
# 忽略所有的 .a 文件
*.a
# 但跟踪所有的 lib.a，即便你在前面忽略了 .a 文件
!lib.a
# 只忽略当前目录下的 TODO 文件，而不忽略 subdir/TODO
/TODO
# 忽略任何目录下名为 build 的文件夹
build/
# 忽略 doc/notes.txt，但不忽略 doc/server/arch.txt
doc/*.txt
# 忽略 doc/ 目录及其所有子目录下的 .pdf 文件
doc/**/*.pdf
```

### 比较

- `$ git diff` ，对比暂存区和工作区（修改的文件）的差异 
- `$ git diff --staged` 或 `$ git diff --cached` ，对比暂存区和 Git 目录（上一次提交的文件）的差异 

### 提交

- `$ git commit`，会打开配置的文本编辑器，以输入提交的描述信息，关闭文件后开始提交更新
- `$ git commit -m Fix some problems`，以参数的形式提交描述信息，不会打开文本编辑器
- `$ git commit -a`，自动暂存工作区修改的文件，然后提交更新，前提是文件已经被追踪，***谨慎使用***
- `$ git commit --amend`，提交并取代上一次的提交历史，用于提交后的小修小补而不扰乱仓库提交历史

### 合并提交

- `$ git cherry-pick <commitid>`，合并某一个提交对象（可以是别的分支上的对象）到当前分支上，\<commitid> 可以是完整或部分的提交对象哈希值

### 删除文件

- `$ git rm filename`，删除工作区和暂存区的文件（这时，工作区和暂存区的文件要保持一致，即工作区修改的文件已被暂存）
- `$ git rm -f filename`，当工作区的文件已修改但是没有暂存时，需要强制删除（有时候作者不知道这个文件没被暂存，强制删除可以保护工作区已修改但未暂存的文件，避免其被误删）
- `$ git rm --cached filename`，有时候想保留工作区的文件，删除暂存区的文件，即不想让 git 继续追踪了，可以使用 --cached 参数只删除暂存区的文件

### 移动文件

- `$ git mv file_from file_to`
- 使用此命令可以进行改名操作，`$ git mv README.md README` 相当于执行这三条命令：`$ mv README.md README`，`$ git rm README.md`，`$ git add README`， 不过在使用其他工具重命名文件时，记得在提交前 git rm 删除旧文件名，再 git add 添加新文件名

### 贮藏工作区

有时候需要切换分支完成紧急工作，但是当前分支工作还未完成，为了保留当前工作区做出的修改，可以使用以下命令：

- `$ git stash`，贮藏工作区修改的内容
- `$ git stash list`，查看贮藏列表
- `$ git stash pop`，恢复工作区现场，并删除贮藏的内容
- `$ git stash apply`，恢复工作区现场，不删除贮藏内容
- `$ git stash apply stash@{0}`，恢复指定的工作区现场，不删除贮藏内容

### 提交日志

- `$ git log`，查看提交历史日志，功能强大

### 撤销

- `$ git reset HEAD filename`，撤销文件的暂存，将修改后的文件从暂存区放回到工作区
- `$ git checkout -- filename` 或 `$ git restore filename`，撤销修改或删除，将工作区文件恢复为暂存区的状态，如果暂存区没有则恢复到上次提交的状态

### 版本回退

- `$ git reset --hard HEAD`，回退到上一次提交的状态
- `$ git reset --hard <commitid>`，回退版本后，恢复到回退前的版本，参数是提交对象的id（哈希值）（完整或部分），如果忘记 commitid 可以通过 `$ git reflog` 查看

### 远程仓库

- `$ git remote add <shortname> <url>`，添加远程仓库，`$ git clone <url>` 命令会自动添加远程仓库并将简写名称设置为 origin
- `$ git remote`，查看远程仓库的名字
- `git ls-remote <remote>`，获取远程仓库的列表
- `$ git remote -v`，查看远程仓库的名字、地址、权限
- `$ git fetch <remote>`，从远程仓库更新数据，参数是远程仓库简称或地址
- `$ git push <remote> <branch>`，将 \<branch> 分支推送到 \<remote> 服务器
- `$ git remote show <remote>`，查看远程仓库信息
- `$ git remote rename <oldname> <newname>`，重命名远程仓库
- `$ git remote remove <remote>` 或 `$ git remote rm <remote>`，移除远程仓库

### 打标签

可以为某一次提交打上一个标签，标志着阶段工作（一个版本）的完成，标签便于记忆，这样可以方便地查找到特定版本

- `$ git tag`，查看所有标签
- `$ git tag -l "v1.8.5*"`，按照规则查找标签，此例子表示查看以 v1.8.5 开头的标签
- `$ git tag -a v1.4 -m "my version 1.4"`，添加附注标签（annotated），默认打在最近一次提交上，-a 选项设置标签名，-m 选项配置标签信息
- `$ git tag v1.4-lw`，添加轻量标签（lightweight），默认打在最近一次提交上，没有额外信息，只有标签名
- `$ git tag -a v1.2 9fceb02`，为历史提交打标签，需要在命令的末尾指定提交的校验和（或部分校验和），可以先通过 `$ git log` 查看历史提交的校验和
- `$ git show <tagname>`，查看标签详情
- `$ git push origin <tagname>`，共享标签，为远程仓库 origin 设置 \<tagname> 标签，当其他人从仓库中克隆或拉取，他们也能得到标签
- `$ git push origin --tags`，一次性推送所有远程仓库没有的标签
- `$ git tag -d <tagname>`，删除本地标签
- `$ git push origin --delete <tagname>`，删除远程仓库的标签
- `$ git push origin :refs/tags/v1.4-lw`，删除远程仓库的标签，含义是，将冒号前面的空值推送到远程标签名
- `$ git checkout <tagname>`，根据标签切换到指定的提交，如果在此提交下进行修改并提交，这样会导致此提交处于分离头指针状态（提交会脱离于分支树，除非通过哈希值查找，否则无法访问），如果你想在此版本的基础上进行修改，需要创建一个新分支并打标签，`$ git checkout -b <newbranch> <tagname>`，然后再提交修改

### 别名

可以为 git 命令取别名

```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
```

# 3 Git 分支

## 分支简介

Git 处理分支的方式可谓是难以置信的轻量，也正因为这一特性，使得 Git 从众多版本控制系统中脱颖而出

### 暂存做了什么？

1. 为每一个文件计算校验和（SHA-1 哈希算法）
2. 把当前版本的文件快照保存到 Git 仓库中 （Git 使用 blob 对象来保存它们）
3. 将校验和加入到暂存区域等待提交

### 提交做了什么？

1. Git 会先计算每一个子目录的校验和
2. 在 Git 仓库中这些校验和保存为树对象
3. Git 会创建一个提交对象，它除了包含上面提到的那些信息外，还包含指向这个树对象（项目根目录）的指针
4. 提交之后，提交对象还会包含一个指向上次提交对象（父对象）的指针

- 提交对象内部的数据结构：1 个提交对象 ==> 1 个树对象 ==> n 个 blob 对象
- 提交对象之间的数据结构：提交对象 A ==> 提交对象 B ==> 提交对象 C

### 什么是分支？

- 分支是一个指针，指向某一个提交对象

### 创建分支做了什么？

- 其实本质上仅仅是创建一个包含所指对象校验和（长度为 40 的 SHA-1 值字符串）的文件（就是一个指针），所以分支的创建和销毁都异常高效

### 如何确定当前分支？

- HEAD指针（头指针）指向当前所在分支指针
- 分支指针会指向当前的提交对象，每次提交完成之后，头指针和分支指针都会自动指向新的提交对象

### 切换分支做了什么？

- 使 HEAD 指向要切换的分支
- 将工作目录恢复成切换分支所指向的快照内容（之前提到的提交对象）

### 合并分支做了什么？

- 快进（Fast-forward）的情况：要合并父子分支（把子分支合并到父分支），此时合并操作并没有任何分歧，这时会直接向前推进父分支指针，最后父子分支指针会指向同一个提交对象。也可以通过 `--no-ff` 参数禁用快进模式，此时会产生分叉情况，即会创建一个新提交（存储合并后的内容），这个新提交对象会有两个父提交：子分支指向的提交、父分支指向的提交，最后父分支指针后移，指向新提交。***快进模式合并的分支在提交历史中看不出来有过合并***
- 分叉（diverged）的情况：要合并兄弟分支（把 A 分支合并到 B 分支），即他们有一个共同的祖先，这时，合并操作会新建一个第三方提交对象，这个对象有两个父提交（ A 分支和 B 分支 ），且B 分支指针会后移到这个对象上（ A 分支的指针不会移动，可以手动删除它 ）
- 分支中有文件产生冲突怎么办？可以使用 `$ git status` 查看冲突状态，手动合并（或使用合并工具 `$ git mergetool`）冲突文件后，再输入`$ git commit` 完成合并

## 分支开发工作流

### 长期分支

项目长期保持多个分支，多条流水线，不同分支具有不同级别的稳定性，当分支具有一定程度的稳定性后，再把它合并入具有更高级别稳定性的分支中，一般稳定分支的指针总是在提交历史中落后一大截，而前沿分支的指针往往比较靠前。

### 主题分支

属于短期分支，它被用来实现单一特性或其相关工作。根据不同主题（主题之间互不干扰）创建分支，完成工作且合并到主线后便删掉此分支，这样不用在乎它们建立的顺序或工作进度，因为每个分支仅与其目标特性相关，并且，在做代码审查之类的工作的时候能更加容易地看出你做了哪些改动。

## 远程分支

### 远程分支？远程跟踪分支？跟踪分支？

- 远程分支是远程仓库中的分支
- 远程跟踪分支是本地的分支，它在本地的克隆仓库里，是对远程分支的引用，并且本地不可控制它的移动，随着不断进行新的提交，远程跟踪分支指针不会移动，它像是一个书签，记录着远程仓库中分支指针在本地分支中的位置
- 跟踪分支是 git 自动创建的本地分支，用于在远程跟踪分支的基础上进行新的工作，随着不断进行新的提交，跟踪分支指针也会随之推进

### 如何区分本地分支和远程跟踪分支？

远程跟踪分支命名格式为 `<remote>/<branch>`，本地分支名称命名格式为 `<branch>`

### 将远程仓库 clone 到本地会创建分支吗？

将远程仓库 clone 到本地会创建 `origin/master` 分支（远程跟踪分支），并创建 `master` （跟踪分支），两个分支都指向同一个提交对象，当你开始在远程分支的基础上工作，并进行提交，`master` 分支会随之后移，而 `origin/master` 会一直指向最初的提交对象

### 远程分支有新的内容怎么办？

当远程分支有新内容，可以执行 `git fetch <remote>` 命令，抓取远程仓库的新提交对象并合并到本地，并将 `origin/master` 分支指向最新的提交对象，如果这时本地已经进行了新的提交，则 `master` 和 `origin/master` 分支会出现分叉

### 可以有多个远程跟踪分支吗？

可以，比如除了有一个项目 Git 服务器 origin，还有另一个内部 Git 服务器 teamone，仅服务于你的某个敏捷开发团队，这时候你在本地会有 `origin/master` 和 `teamone/master` 两个远程跟踪分支

### 如何推送自己的分支？

运行 `git push <remote> <branch>` 可以将本地的 \<branch> 分支推送到远程服务器 \<remote> 的 \<branch> 分支上（需要有服务器权限），别人可以通过 fetch 获取你推送的分支，并且在本地创建一个新分支 `<remote>/<branch>`（远程跟踪分支），如果需要在此分支的基础上继续工作，可以通过 `$ git checkout -b <newbranchname> <originbranch>` 创建一个新的本地分支，并在本地分支上进行新的提交

### 跟踪分支都是自动创建的吗？

git 只会自动创建 master 跟踪分支，如果想创建其他远程跟踪分支的跟踪分支，可以通过 `$ git checkout -b <newbranchname> <originbranch>` 使用自定义的跟踪分支名称，或者使用 `$ git checkout --track <remote>/<branch>` 创建默认的跟踪分支名称（\<branch>），或者对于一个存在的远程跟踪分支 \<remote>/\<branch> ，执行 `$ git checkout <branch>` ，git 会检测出这是一个跟踪分支并自动匹配。更多创建跟踪分支方式详见相关命令。

## 变基

变基（rebase），将一个分支 A 的内容变基到分支 B 上，会执行以下操作：将 A 和 B 的内容合并到一个新提交对象中，这个提交对象在 B 分支后，这时 A 分支指针指向新提交对象，并且清除分支 A 之前的提交记录，仿佛 A 分支从没存在过，和合并相比，这样的方式使提交历史更加简洁，但是如果将远程分支进行变基操作会产生一系列问题（变基会删除的远程分支上的提交记录，可能其他协作者正在此分支上进行新的工作，如果协作者将这个分支推送，已经被变基抛弃的提交又会被恢复），所以一般对于个人本地分支可以采用变基，对于远程分支变基操作可能会严重影响其他协作者的工作

***如果提交存在于你的仓库之外，而别人可能基于这些提交进行开发，那么不要执行变基。***

## 相关命令

### 查看分支

- `$ git branch`，查看分支列表
- `$ git branch -v`，查看分支列表以及看每一个分支的最后一次提交信息
- `$ git branch --merged`，查看已合并分支
- `$ git branch --no-merged`，查看未合并的分支

### 创建分支

- `$ git branch <branchname>`，创建分支（但不切换）
- `git branch -vv`，查看所有本地分支，以及他们正在跟踪的远程分支和领先（本地提交未推送）或落后（服务器的提交没有拉取）信息，注意这些信息是来自于最后一次拉取的远程仓库数据，如果需要和实时信息对比，可以先执行 `git fetch --all` 拉取最新数据
- `git branch -u <remote>/<branch>`，设置当前所在分支为 `<remote>/<branch>` 的跟踪分支

### 切换分支

- `$ git checkout <branchname>`，切换到某个分支
- `$ git switch <branchname>`，切换到某个分支，更直白且会在切换时检查工作区是否修改以发出警告，***推荐使用***
- `$ git checkout -b <newbranchname> <originbranch>`，创建并切换分支，`<originbranch>` 表示创建新分支的起点分支，可省略（表示在当前分支创建一个新分支）
- `$ git switch -c <branchname>`，创建并切换分支，更直白且会在切换时检查工作区是否修改以发出警告，***推荐使用***

### 合并分支

- `$ git merge <branchname>`，合并分支 \<branchname> 到当前所在分支
- `$ git merge --no-ff <branchname>`，合并分支，但是不使用 fast-forward 模式，此时合并会创建一个新提交，并且当前所在分支指针会指向这个新提交，\<branchname> 分支指针不会移动
- `$ git mergetool`，使用合并工具

### 删除分支

- `$ git branch -d <branchname>`，删除分支（删除的是指针）
- `$ git branch -D <branchname>`，强行删除分支（哪怕这个分支还没有合并）

### 远程分支

- `$ git checkout --track <remote>/<branch>` 创建并切换到新的跟踪分支，跟踪分支的名称为  \<branch>
- `$ git push <remote> <branch>`，将本地分支 \<branch> 推送到远程仓库 \<remote> 的分支 \<branch>
- `$ git push <remote> --delete <branch>`，删除服务器上的远程分支
- `$ git pull <remote> <branch>`，拉取然后合并到当前所在分支，相当于先执行 `git fetch <remote>` ，然后执行 `git merge <remote>/<branch>`

### 变基

- `git rebase <branch>`，将所在分支变基到 \<branch> 分支上
- `git rebase <basebranch> <topicbranch>`，将 \<topicbranch> 分支变基到 \<basebranch> 分支上

# 4 分布式 Git

## 分布式工作流程

### 集中式工作流

有一个中心仓库，其他协作者作为节点，将自己的工作与之同步。这意味着如果两个开发者从中心仓库克隆代码下来，同时作了一些修改，那么只有第一个开发者可以顺利地把数据推送回共享服务器。 第二个开发者推送修改时，会遭到服务器拒绝，会被告知她的修改正通过非快进式（non-fast-forward）的方式推送，必须先将第一个人的工作合并进来，再进行推送。

### 集成管理者工作流

工作流程如下：

1. 项目维护者推送到主仓库。
2. 贡献者克隆此仓库，做出修改。
3. 贡献者将数据推送到自己的公开仓库。
4. 贡献者给维护者发送邮件，请求拉取（pull request）自己的更新。
5. 维护者在自己本地的仓库中，将贡献者的仓库加为远程仓库并合并修改。
6. 维护者将合并后的修改推送到主仓库。

这是 GitHub 和 GitLab 等集线器式（hub-based）工具最常用的工作流程。人们可以容易地将某个项目派生成为自己的公开仓库，向这个仓库推送自己的修改，并为每个人所见。这么做最主要的优点之一是你可以持续地工作，而主仓库的维护者可以随时拉取你的修改。贡献者不必等待维护者处理完提交的更新——每一方都可以按照自己的节奏工作。

### 主管与副主管工作流

工作流程如下：

1. 普通开发者在自己的主题分支上工作，并根据 master 分支进行变基。 这里是主管推送的参考仓库的
master 分支。
2. 副主管将普通开发者的主题分支合并到自己的 master 分支中。
3. 主管将所有副主管的 master 分支并入自己的 master 分支中。
4. 最后，主管将集成后的 master 分支推送到参考仓库中，以便所有其他开发者以此为基础进行变基。

这种工作流程并不常用，只有当项目极为庞杂，或者需要多级别管理时，才会体现出优势。 利用这种方式，项目总负责人（即主管）可以把大量分散的集成工作委托给不同的小组负责人分别处理，然后在不同时刻将大块的代码子集统筹起来，用于之后的整合。

# 5 Github

## 本地 Git 连接 Github 远程仓库

1. 创建本地目录，进入目录后打开 Git Bash，在当前目录下执行 `git init`
2. 向该目录下添加文件，并存入暂存区，`git add --all`将目录下所有文件加入暂存区
3. 提交，`git commit -m '提交信息'`
4. 查看用户目录（ windows 系统为 C:\Users\你的用户名 ）下是否有 .ssh 目录，并查看目录下是否有 id_rsa 和 id_rsa.pub 这两个文件，有的话跳到第 6 步
5. `ssh-keygen -t rsa -C "你的 github 邮箱"` 创建密钥对，保存位置默认，密码短语为空
6. 登录 github，在设置中找到 SSH and PGP keys ，新建 SSH key，title 自取，key 的内容是 id_rsa.pub 的全部内容
- 为什么需要让服务器知道公钥信息？服务器使用公钥加密，用户通过私钥解密，服务器通过比对解密的信息可以确认用户的身份
7. `ssh -T git@github.com` 命令测试连接，第一次连接会有提示让用户验证 SSH 密钥指纹（可以在[官方文档](https://docs.github.com/zh/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints)中比对公钥指纹），比较没有问题后输入 yes 并回车
- 为什么需要公钥指纹？用户第一次通过 SSH 登录服务器时需要验证服务器的身份（防止中间人攻击），公钥指纹是对公钥的签名，会被公开在官网上，用户只要确定这个公钥是真实的就可以避免中间人攻击（哪怕中间人用这个密钥指纹伪造了一个服务器，只要中间人没有私钥，就无法解密用户通过公钥加密的内容），第一次登陆一但确认了公钥指纹，这个指纹会保存到 known_hosts 文件中，用户再次登录时会自动比对验证公钥指纹
8. `git remote add origin '仓库SSH链接'`添加远程仓库，仓库的SSH链接可以在 Github 上获取（点击 Code 按钮）
9. `git push -u origin master`推送到远程仓库，带上 -u 参数其实就相当于记录了push到远端分支的默认值，这样当下次我们还想要继续push的这个远端分支的时候推送命令就可以简写成 git push 即可