---
layout:     post
title:      "关于git 无法commit的问题"
subtitle:   "git process"
date:       2017-03-02
author:     "Junhui"
header-img: "img/bg.jpg"
tags:
    - 前端开发
    - git
---

#### 关于git 无法commit问题

##### commit时候出现以下提醒
>$ Another git process seems to be running in this repository, e.g.

>an editor opened by 'git commit'. Please make sure all processes 
are terminated then try again. If it still fails, a git process 
may have crashed in this repository earlier: 
remove the file manually to continue.

大致意思就是你已经提交了一commit，该进程卡在这里了，所以无法提交
使用

>$ rm -f ./.git/index.lock 命令

结束该进程

杀死该进程后即可提交

  




