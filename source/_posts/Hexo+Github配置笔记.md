---
title: Hexo+Github配置笔记
date: 2020-05-21 22:38:37
tags: Hexo
categories: Note
archives: Note
---

在一个仓库中创建两个分支，分别用于管理站点源文件和站点配置文件
<!-- more -->
---

## 本地配置

### 安装 [nodejs](https://nodejs.org/)
检查是否安装成功
```bash
node –v  
npm -v
```
### 安装[git](https://git-scm.com/downloads)
检查是否安装成功
```bash
git --version
```
### hexo安装和配置
创建`blog`目录，进入目录。这个目录就是存放所有配置文件，以及后续更新blog的目录。

#### 安装hexo
```bash
npm install -g hexo-cli
```
如果命令行安装时很慢，可以尝试先设置国内镜像再下载
```bash
npm config set registry:https://registry.npm.taobao.org
```
或者手动去下载([hexo-starter](https://github.com/hexojs/hexo-starter)) 下载完后，解压放到 blog 目录下，也是一样的效果

#### 初始化hexo
```bash
hexo init
```
此时，基本的配置目录已经出来了，需要把我们自己的".md"博客文件放到`blog\source\_posts`目录下，后续`hexo generate`会自动将其生成到网页中

#### 生成网页
``` bash
hexo generate
```
此时，我们会发现`blog`目录下多了一个`public`目录，这就是整个网站的源文件，后续发布到`master`分支的就是这个目录的内容

#### 本地测试
在本地启动server
``` bash
hexo server
```
打开 http://localhost:4000/ 就可以看到默认的博客的主页了  

#### 更换主题
[next](https://github.com/theme-next/hexo-theme-next.git) (更多主题: [themes](https://hexo.io/themes/)) 将主题包解压，放入 blog/themes/next 目录下  

配置 blog/_config.yml 中的 theme 字段为你的主题名称
```bash
theme: next
```
> ***Note***  
> `blog/_config.yml`是hexo的配置文件  
> `blog/themes/next/_config.yml`是主题next的配置文件


---
## 发布到github.io 

### 创建仓库
仓库名是固定的，必须是你的名字加上".github.io"后缀  
我的名字github名字是cellspace，所以就必须是：cellspace.github.io

### 创建两个分支：master 与 hexo 
点击仓库主上的"branch:master"创建一个新的分支hexo,   
并设置hexo为默认分支:   
`Settings` ==> `Branches` ==> `选择"hexo"` ==> `Update`  
> ***Note***:  
>  `master`: 用来存放`hexo generate`自动生成的网页的源文件  
>  `hexo`: 用来存放hexo的配置文件，以及我们所写的".md"类型的博客文件    
#### master分支配置
配置本地`blog/_config.yml`中的`deploy`字段
```yml
deploy:
  type: git
  repository: git@github.com:UserName/UserName.github.io.git
  branch: master
```
发布到github
```bash
hexo deploy
```
发布完成后访问：https://UserName.github.io 就可以看到你的博客了

#### hexo分支配置   
由于是首次配置，且前面已经创建了blog目录，不能直接clone，需要在生成git配置文件，并将本地git与远端关联 
```
cd blog
git init
git checkout -b hexo
git remote add origin git@github.com:UserName/UserName.github.io.git
git branch --set-upstream-to=origin/hexo hexo
```
后续如果想要在别的电脑上更新,直接clone即可
```bash
git clone -b BranchName --single-branch git@github.com:UserName/UserName.github.io.git
```
提交hexo分支中的配置文件
```bash
git add *
git commit -m "none"
git push
```