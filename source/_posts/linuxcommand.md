---
title: Linux常用命令
date: 2018-03-09 14:52:53
tags: 
---

记录本人日常使用的Linux命令 , 持续更新...

<!--more-->

### 文件
``` sh
# 进入 '/root' 目录
cd /root

# 进入当前用户目录
cd 

# 返回上一级目录
cd ..

# 返回上两级目录(以此类推)
cd ../..

# 显示当前所在工作目录
pwd

# 查看目录中的文件 
ls

# 查看当前目录下的文件和目录的详细信息
ls -l

# 显示隐藏文件
ls -a

# 创建一个叫做 'dir1' 的目录' 
mkdir dir1

# 同时创建两个目录 
mkdir dir1 dir2

# 创建一个目录树 
mkdir -p /tmp/dir1/dir2

# 删除一个叫做 'file1' 的文件' 
rm -f file1

# 删除一个叫做 'dir1' 的目录' 
rmdir dir1

# 删除一个叫做 'dir1' 的目录并同时删除其内容
rm -rf dir1

# 重命名/移动 一个目录 
mv dir new_dir

# 复制一个文件
cp file1 file2

# 复制一个目录下的所有文件到当前工作目录 
cp dir/* .

# 复制一个目录到当前工作目录 
cp -a /tmp/dir1 .

# 复制一个目录 
cp -a dir1 dir2

# 创建一个指向文件或目录的软链接 
ln -s file1 lnk1

# 创建一个指向文件或目录的物理链接 
ln file1 lnk1

# 显示当前目录下文件和目录的树形结构
# 没有该命令需要（yum install -y tree）进行安装
tree
```

### 系统操控
``` sh
# 重启(2) 
reboot

# 关闭系统(2) 
init 0

# 注销 
logout

# 关闭系统(3) 
telinit 0

# 关闭系统(1) 
shutdown -h now

# 按预定时间关闭系统 
shutdown -h hours:minutes &

# 取消按预定时间关闭系统 
shutdown -c

# 重启(1) 
shutdown -r now
```