本地配置
1.安装 [nodejs](https://nodejs.org/)
命令行检查是否安装成功
node –v  
npm -v
2.安装 [git](https://git-scm.com/downloads)
命令行检查是否安装成功
git --version
3.安装hexo
npm install -g hexo-cli (npm install hexo)
如果速度太慢可以设置国内镜像
 npm config set registry https://registry.npm.taobao.org
4.创建blog目录，进入目录：
(1)初始化hexo
hexo init
可能会很慢，可以手动去下载 ：[hexo-starter](https://github.com/hexojs/hexo-starter)，解压放到 blog 目录下
下载主题 ：[matery](https://github.com/blinkfox/hexo-theme-matery) ，解压放入blog/themes 目录下
更多主题 ：[themes](https://hexo.io/themes/)
配置 _config.yml 中的 theme 字段为你的主题目录
theme: matery
(2)安装必要的依赖
 npm install
(3)生成网页
 hexo generate (hexo g)
(4)本地测试
 hexo server (hexo s)
打开 http://localhost:4000/
(5)安装 hexo-deployer-git
 npm install hexo-deployer-git --save
(6)关联并发布到github
首先配置 _config.yml 中的 deploy 字段
deploy:
  type: git
  repository: git@github.com:your_name/your_name.github.io.git
  branch: master
发布到github
 hexo deploy (hexo d)