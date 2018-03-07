---
title: Git常用命令
date: 2018-03-07 11:06:53
tags: 
---
### 一、新建代码库

> \# 在当前目录新建一个Git代码库
>
> $ git init
> 
> \# 新建一个目录，将其初始化为Git代码库
>
> $ git init [project-name]
> 
> \# 下载一个项目和它的整个代码历史
>
> $ git clone [url]

### 二、配置

Git的设置文件为.gitconfig，它可以在用户主目录下（全局配置），也可以在项目目录下（项目配置）。

> \# 显示当前的Git配置
> 
> $ git config --list
> <br/><br>
> \# 编辑Git配置文件
> 
> $ git config -e [--global]
> <br/><br>
> \# 设置提交代码时的用户信息
> 
> $ git config [--global] user.name "[name]"

> $ git config [--global] user.email "[email address]"

### 三、增加/删除文件

> \# 添加指定文件到暂存区<br/>
> $ git add [file1] [file2] ...
> <br/><br/>
> \# 添加指定目录到暂存区，包括子目录<br/>
> $ git add [dir]
> <br/><br/>
> \# 添加当前目录的所有文件到暂存区<br/>
> $ git add .
> <br/><br/>
> \# 添加每个变化前，都会要求确认<br/>
> \# 对于同一个文件的多处变化，可以实现分次提交<br/>
> $ git add -p
> <br/><br/>
> \# 删除工作区文件，并且将这次删除放入暂存区<br/>
> $ git rm [file1] [file2] ...
> <br/><br/>
> \# 停止追踪指定文件，但该文件会保留在工作区<br/>
> $ git rm --cached [file]
> <br/><br/>
> \# 改名文件，并且将这个改名放入暂存区<br/>
> $ git mv [file-original] [file-renamed]

### 四、代码提交

> \# 提交暂存区到仓库区<br/>
> $ git commit -m [message]<br/>
> <br/>
> \# 提交暂存区的指定文件到仓库区<br/>
> $ git commit [file1] [file2] ... -m [message]<br/>
> <br/>
> \# 提交工作区自上次commit之后的变化，直接到仓库区<br/>
> $ git commit -a<br/>
> <br/>
> \# 提交时显示所有diff信息<br/>
> $ git commit -v<br/>
> <br/>
> \# 使用一次新的commit，替代上一次提交<br/>
> \# 如果代码没有任何新变化，则用来改写上一次commit的提交信息<br/>
> $ git commit --amend -m [message]<br/>
> <br/>
> \# 重做上一次commit，并包括指定文件的新变化<br/>
> $ git commit --amend [file1] [file2] ...<br/>

### 五、分支

> \# 列出所有本地分支<br/>
> $ git branch<br/>
> <br/>
> \# 列出所有远程分支<br/>
> $ git branch -r<br/>
> <br/>
> \# 列出所有本地分支和远程分支<br/>
> $ git branch -a<br/>
> <br/>
> \# 新建一个分支，但依然停留在当前分支<br/>
> $ git branch [branch-name]<br/>
> <br/>
> \# 新建一个分支，并切换到该分支<br/>
> $ git checkout -b [branch]<br/>
> <br/>
> \# 新建一个分支，指向指定commit<br/>
> $ git branch [branch] [commit]<br/>
> <br/>
> \# 新建一个分支，与指定的远程分支建立追踪关系<br/>
> $ git branch --track [branch] [remote-branch]<br/>
> <br/>
> \# 切换到指定分支，并更新工作区<br/>
> $ git checkout [branch-name]<br/>
> <br/>
> \# 切换到上一个分支<br/>
> $ git checkout -<br/>
> <br/>
> \# 建立追踪关系，在现有分支与指定的远程分支之间<br/>
> $ git branch --set-upstream [branch] [remote-branch]<br/>
> <br/>
> \# 合并指定分支到当前分支<br/>
> $ git merge [branch]<br/>
> <br/>
> \# 选择一个commit，合并进当前分支<br/>
> $ git cherry-pick [commit]<br/>
> <br/>
> \# 删除分支<br/>
> $ git branch -d [branch-name]<br/>
> <br/>
> \# 删除远程分支<br/>
> $ git push origin --delete [branch-name]<br/>
> $ git branch -dr [remote/branch]<br/>

### 六、标签

> \# 列出所有tag<br/>
> $ git tag<br/>
> <br/>
> \# 新建一个tag在当前commit<br/>
> $ git tag [tag]<br/>
> <br/>
> \# 新建一个tag在指定commit<br/>
> $ git tag [tag] [commit]<br/>
> <br/>
> \# 删除本地tag<br/>
> $ git tag -d [tag]<br/>
> <br/>
> \# 删除远程tag<br/>
> $ git push origin :refs/tags/[tagName]<br/>
> <br/>
> \# 查看tag信息<br/>
> $ git show [tag]<br/>
> <br/>
> \# 提交指定tag<br/>
> $ git push [remote] [tag]<br/>
> <br/>
> \# 提交所有tag<br/>
> $ git push [remote] --tags<br/>
> <br/>
> \# 新建一个分支，指向某个tag<br/>
> $ git checkout -b [branch] [tag]<br/>

### 七、查看信息

> \# 显示有变更的文件<br/>
> $ git status<br/>
> <br/>
> \# 显示当前分支的版本历史<br/>
> $ git log<br/>
> <br/>
> \# 显示commit历史，以及每次commit发生变更的文件<br/>
> $ git log --stat<br/>
> <br/>
> \# 搜索提交历史，根据关键词<br/>
> $ git log -S [keyword]<br/>
> <br/>
> \# 显示某个commit之后的所有变动，每个commit占据一行<br/>
> $ git log [tag] HEAD --pretty=format:%s<br/>
> <br/>
> \# 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件<br/>
> $ git log [tag] HEAD --grep feature<br/>
> <br/>
> \# 显示某个文件的版本历史，包括文件改名<br/>
> $ git log --follow [file]<br/>
> $ git whatchanged [file]<br/>
> <br/>
> \# 显示指定文件相关的每一次diff<br/>
> $ git log -p [file]<br/>
> <br/>
> \# 显示过去5次提交<br/>
> $ git log -5 --pretty --oneline<br/>
> <br/>
> \# 显示所有提交过的用户，按提交次数排序<br/>
> $ git shortlog -sn<br/>
> <br/>
> \# 显示指定文件是什么人在什么时间修改过<br/>
> $ git blame [file]<br/>
> <br/>
> \# 显示暂存区和工作区的代码差异<br/>
> $ git diff<br/>
> <br/>
> \# 显示暂存区和上一个commit的差异<br/>
> $ git diff --cached [file]<br/>
> <br/>
> \# 显示工作区与当前分支最新commit之间的差异<br/>
> $ git diff HEAD<br/>
> <br/>
> \# 显示两次提交之间的差异<br/>
> $ git diff [first-branch]...[second-branch]<br/>
> <br/>
> \# 显示今天你写了多少行代码<br/>
> $ git diff --shortstat "@{0 day ago}"<br/>
> <br/>
> \# 显示某次提交的元数据和内容变化<br/>
> $ git show [commit]<br/>
> <br/>
> \# 显示某次提交发生变化的文件<br/>
> $ git show --name-only [commit]<br/>
> <br/>
> \# 显示某次提交时，某个文件的内容<br/>
> $ git show [commit]:[filename]<br/>
> <br/>
> \# 显示当前分支的最近几次提交<br/>
> $ git reflog<br/>
> <br/>
> \# 从本地master拉取代码更新当前分支：branch 一般为master<br/>
> $ git rebase [branch]<br/>

### 八、远程同步

> \# 下载远程仓库的所有变动<br/>
> $ git fetch [remote]<br/>
> <br/>
> \# 显示所有远程仓库<br/>
> $ git remote -v<br/>
> <br/>
> \# 显示某个远程仓库的信息<br/>
> $ git remote show [remote]<br/>
> <br/>
> \# 增加一个新的远程仓库，并命名<br/>
> $ git remote add [shortname] [url]<br/>
> <br/>
> \# 取回远程仓库的变化，并与本地分支合并<br/>
> $ git pull [remote] [branch]<br/>
> <br/>
> \# 上传本地指定分支到远程仓库<br/>
> $ git push [remote] [branch]<br/>
> <br/>
> \# 强行推送当前分支到远程仓库，即使有冲突<br/>
> $ git push [remote] --force<br/>
> <br/>
> \# 推送所有分支到远程仓库<br/>
> $ git push [remote] --all<br/>

### 九、撤销

> \# 恢复暂存区的指定文件到工作区<br/>
> $ git checkout [file]<br/>
> <br/>
> \# 恢复某个commit的指定文件到暂存区和工作区<br/>
> $ git checkout [commit] [file]<br/>
> <br/>
> \# 恢复暂存区的所有文件到工作区<br/>
> $ git checkout .<br/>
> <br/>
> \# 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变<br/>
> $ git reset [file]<br/>
> <br/>
> \# 重置暂存区与工作区，与上一次commit保持一致<br/>
> $ git reset --hard<br/>
> <br/>
> \# 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变<br/>
> $ git reset [commit]<br/>
> <br/>
> \# 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致<br/>
> $ git reset --hard [commit]<br/>
> <br/>
> \# 重置当前HEAD为指定commit，但保持暂存区和工作区不变<br/>
> $ git reset --keep [commit]<br/>
> <br/>
> \# 新建一个commit，用来撤销指定commit<br/>
> \# 后者的所有变化都将被前者抵消，并且应用到当前分支<br/>
> $ git revert [commit]<br/>
> <br/>
> \# 暂时将未提交的变化移除，稍后再移入<br/>
> $ git stash<br/>
> $ git stash pop<br/>

### 十、其他

> \# 生成一个可供发布的压缩包<br/>
> $ git archive<br/>