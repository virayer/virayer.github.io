---
title: Windows下安装Hexo
date: 2018-11-29 17:00:00
tags: 
---
# Windows下安装Hexo

## 一、安装node.js

1. 进入nodejs官网 https://nodejs.org

2. 下载LTS（Long Time Support）长时间支持版本

3. 选择安装目录，一直下一步直到安装成功

##  二、安装git

1. 进入git官网 https://git-scm.com/
2. 下载Windows版本
3. 安装直到完成

## 三、安装hexo

> 官网：https://hexo.io/zh-cn/

1. 在目录右击，点击`git bash here`
2. 安装hexo

```sh
npm install -g hexo-cli
npm install hexo --save
npm install --save hexo-deployer-git
npm install hexo-server --save
```

3. 检测hexo是否安装成功
```sh
hexo -v
```
3. 安装已存在目录的package.json

```sh
npm install
```



