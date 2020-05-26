---
title: Hexo+Github配置笔记
date: 2020-05-21 22:38:37
tags: Hexo
categories: Note
archives: Note
---

在一个仓库中创建两个分支，分别用于管理站点源文件，和站点配置文件
<!-- more -->
## 本地配置

### 安装 nodejs
下载地址：[nodejs](https://nodejs.org/) <br>
检查是否安装成功
```bash
node –v  
npm -v
```
### 安装git
下载地址：[git](https://git-scm.com/downloads) <br>
检查是否安装成功
```bash
git --version
```
### hexo安装和配置
创建blog目录，进入目录：<br>
设置国内镜像
```bash
npm config set registry:https://registry.npm.taobao.org
```
###安装hexo
```bash
npm install hexo --save
```
#### 初始化hexo
```bash
hexo init
```
可能会很慢，可以手动去下载 ：[hexo-starter](https://github.com/hexojs/hexo-starter) &ensp;下载完后，解压放到 blog 目录下<br>
下载主题 ：[next](https://github.com/theme-next/hexo-theme-next.git)&ensp;(更多主题 ：[themes](https://hexo.io/themes/))  &ensp;将主题包解压，放入 blog/themes/next 目录下 <br>

配置 _config.yml 中的 theme 字段为你的主题目录 <br>
```bash
theme: next
```
#### 安装必要的依赖
``` bash
npm install
```
#### 生成网页
``` bash
hexo generate (hexo g)
```
#### 本地测试
``` bash
hexo server (hexo s)
```
打开 http://localhost:4000/ 就可以看到本地的博客的主页了

---
 ## 远程仓库Github配置  
 
 ### 创建仓库
 &emsp;&ensp;仓库名是固定的，必须是你的名字加上".github.io"后缀：UserName.github.io
 ### 创建两个分支：master 与 hexo
 &emsp;&ensp;点击仓库主上的"branch:master"创建一个新的分支hexo <br>
 &emsp;&ensp;**master分支:** 用来存放博客网页的源文件（hexo deploy 默认推送到master）<br>
 &emsp;&ensp;**hexo分支:** 用来存放hexo的配置文件
 ### 设置hexo为默认分支
 &emsp;&ensp;Settings ==> Branches ==> 选择"hexo" ==> Update
 ### 克隆仓库远程仓库到本地：
  &emsp;&ensp;克隆hexo分支到本地，也可以不加-b选项，克隆整个仓库
 ```bash
 git clone -b hexo --single-branch git@github.com:UserName/UserName.github.io.git
 or
 git clone git@github.com:UserName/UserName.github.io.git
 ```
 ### 安装 hexo-deployer-git
 ```bash
  npm install hexo-deployer-git --save
 ```
 ### 关联并发布到github
  &emsp;&ensp;首先配置 _config.yml 中的 deploy 字段
  ```bash
  deploy:
    type: git
    repository: git@github.com:UserName/UserName.github.io.git
    branch: master
  ```
 &emsp;&ensp;发布到github
 ```bash
  hexo deploy (hexo d)
 ```
 &emsp;&ensp;发布完成后访问：https://UserName.github.io 就可以看到你的博客了
 ### 利用hexo分支管理hexo配置文件
  &emsp;&ensp;设置远程分支和本地分支的关联
 ```bash
 git branch --set-upstream-to=origin/<branch> <local_branch>
 ```

 &emsp;&ensp;将配置文件提交到远程hexo分支，如果不是hexo要先切换到hexo分支
 ```bash
 git checkout hexo
 git add *
 git commit -m "none"
 git push
 ```
