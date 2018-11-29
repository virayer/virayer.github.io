---
title: Linux安装Nginx
date: 2018-11-29 16:00:00
tags: 
---
### centos使用如下指令
#### 安装make：
```
yum -y install gcc automake autoconf libtool make
```

#### 安装g++:
```
yum -y install gcc gcc-c++
```

<!-- more -->

### 下面正式开始
---------------------------------------------------------------------------
一般我们都需要先装pcre, zlib，前者为了重写rewrite，后者为了gzip压缩。
#### 1.选定源码目录
可以是任何目录，本文选定的是/usr/local/src
```
cd /usr/local/src
```

#### 2.安装PCRE库
```
yum -y install pcre-devel
```

#### 3.安装zlib库
```
yum -y install zlib-devel
```

#### 4.安装ssl和安装sha1
```
yum -y install openssl openssl-devel
yum -y install perl-Digest-SHA1.x86_64
```

#### 5.安装nginx

Nginx 一般有两个版本，分别是稳定版和开发版，您可以根据您的目的来选择这两个版本的其中一个，下面是把 Nginx 安装到 /usr/local/nginx 目录下的详细步骤：
```
wget http://nginx.org/download/nginx-1.15.1.tar.gz
tar -zxvf nginx-1.15.1.tar.gz
cd nginx-1.15.1

./configure --sbin-path=/usr/local/nginx/sbin/nginx \
--conf-path=/usr/local/nginx/conf/nginx.conf \
--pid-path=/usr/local/nginx/nginx.pid \
--with-http_ssl_module

make && make install
```