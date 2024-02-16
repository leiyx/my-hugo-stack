---
title: Git使用笔记
description: 强大的工具Git
slug: git
date: 2024-01-06 00:00:00+0000
image: cover.jpg
categories:
    - 开发工具
tags:
    - 开发工具
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---
## 概念



- **工作区：**就是你在电脑里能看到的目录。
- **暂存区：**英文叫 stage 或 index。一般存放在 **.git** 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
- **版本库：**工作区有一个隐藏目录 **.git**，这个不算工作区，而是 Git 的版本库。
- **远程仓库**：github仓库

- [ ] 四者关系图！

## .git文件夹解析

Git会将远端与本地的commits保存在 `./.git/objects` 文件夹下。Git通过利用分支的refs来区分远端和本地的commits。本地分支的refs都被保存在`./.git/refs/heads/`文件夹下。





- 文件**HEAD**：文件指向当前工作的分支
- 文件**index**：保存**暂存区**信息
- 目录**objects**：用于存储Git中的所有对象（数据对象、树对象、提交对象、标签对象）
- 目录**refs**：存储指向提交对象的指针
  - 本地分支的refs都被保存在`./.git/refs/heads/`文件夹下
  - 远端分支的refs存储在`./.git/refs/remotes`文件夹下



- 文件description：用来显示对仓库的描述信息

- 目录hooks

- 目录info

  



## 命令



### 基础命令





```shell
git init

git status

git add .
git add file_path

git commit -m "commit-message"

git push <repo> <local_branch>:<remote_branch>

git pull <repo> <remote_branch>:<local_branch>

git log [--oneline] [--author=Linus] [-<num>]

git clone <repo> [<directory>]

git config --list
git config -l

git config [--global] user.name "runoob"
git config [--global] user.email test@runoob.com



```



### reset



```shell
git reset [--soft | --mixed | --hard] <head>
```

可选参数：

- mixed，默认方式，用于重置暂存区的文件与上一次的提交(commit)保持一致，工作区文件内容保持不变。
- soft， 用于回退到某个版本
- hard，撤销工作区中所有未提交的修改内容，将暂存区与工作区都回到上一次版本，并删除之前的所有信息提交

head 说明：

- HEAD 表示当前版本
- HEAD^ 上一个版本
- HEAD^^ 上上一个版本
- HEAD^^^ 上上上一个版本
- 以此类推...

可以使用 ～数字表示

- HEAD~0 表示当前版本
- HEAD~1 上一个版本
- HEAD^2 上上一个版本
- HEAD^3 上上上一个版本
- 以此类推...



### cherry-pick

```shell
git remote
git remote add origin_xxx repo_url
git fetch <remote-repo> <branch>
git cherry-pick commit-id
# 如果有冲突，解决冲突

# 回到执行 cherry-pick 前的状态
git cherry-pick --abort
```

### rebase



```shell
git rebase -i commit-id

# 回到执行 rebase 前的状态
git rebase --abort
```





### fetch和merge

``git pull`` 等价于``git fetch + git merge``，

```shell
# 下载了远端的内容，但也不会更新你本地仓库的版本状态

# fetch仓库中所有分支。同时也会下载指定远端的所有commits和文件。
# 未指定<remote-repo>的话，使用origin
git fetch <remote-repo>
# 与上同，只fetch指定分支
git fetch <remote-repo> <branch>
```



```shell

```





### 分支操作

```shell
git branch <branchname>
git checkout <branchname>
git checkout -b <branchname>

# 合并 <branchname> 到当前分支
git merge <branchname> 

git branch
git branch -r
git branch -a

git branch -d <branchname>
```



### 标签





## 常用操作

将本地分支与远程分支同步:

```shell

```

