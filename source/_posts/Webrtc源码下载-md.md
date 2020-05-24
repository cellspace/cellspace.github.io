---
title: Webrtc源码下载
date: 2020-05-24 14:52:02
tags: WebRTC
categories: OpenSource
---

<br>
[时间]:May 24 2020  &nbsp;&nbsp;&nbsp;&nbsp; [环境]：windows + vs2019 <br>
<br>
1.设置命令行代理(需要打开你的梯子，本地端口根据自己的情况自行修改，我的是1080)
```bash
set http_proxy=127.0.0.1:1080
set https_proxy=127.0.0.1:1080
```

2.下载depot_tools

```bash
git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git
```

3.将depot_tools的路径设置到环境变量

4.开始下载
```bash
fetch  --nohooks webrtc

gclient sync
```
5.设置必要的环境变量

```bash
set GCLIENT_PY3 = 1    
set WINDOWSSDKDIR = D:\Windows Kits\10
set vs2019_install=C:\Program Files (x86)\Microsoft Visual Studio\2019\Community  
set GYP_MSVS_OVERRIDE_PATH=C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\
set GYP_GENERATORS=msvs-ninja,ninja
```

6.生成vs2019工程
```bash
gn gen ../vs2019_prj --ide=vs2019
```
