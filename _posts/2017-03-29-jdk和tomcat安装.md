---
layout:     post
title:      "JDK和tomcat安装"
subtitle:   "工具"
date:       2017-03-29
author:     "Junhui"
header-img: "img/post-bg.jpg"
tags:
    - 工具使用
---

#### bgcloud 前端项目环境搭建 （inellij）

一.  配置jdk，JDK是 Java 语言的软件开发工具包，主要用于移动设备、嵌入式设备上的java应用程序。JDK是整个java开发的核心，它包含了JAVA的运行环境，JAVA工具和JAVA基础的类库。安装jdk是首要任务
jdk下载可以直接到官网下载，[jdk官网下载](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

二. 下载完毕需要配置环境变量
用户变量是针对用户的不同环境变量会随着用户变量的不同而变化，而系统变量是全局性的，针对所有用户；
    右键点击我的电脑-属性-高级-环境变量
    1. JAVA_HOME指明的是JDK的安装路径，就是JDK的安装路径或者是解压路径，我的路径是`E:\jdk1.7.0_51_32\jdk1.7.0_51`此路径下包括lib，bin，jre等文件夹，
    2. CLASSPATH为java加载类（class or lib）路径，只有类在classpath中，java命令才能识别，设为：

`.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar (要加.表示当前路径) `
    
 3.path使得系统可以在任何路径下识别java命令，设为：
    `%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin ` 我的win10 这样设置是不生效的，所以需要单独设置两个即
    ` %JAVA_HOME%\bin`和`%JAVA_HOME%\jre\bin `
    %JAVA_HOME%就是引用前面指定的JAVA_HOME； 
三. 测试环境变量
运行（win+r） 键入cmd；
输入命令` java -version`  `java` 和`javac` 三个命令，出现画面，说明配置成功；如果出现
“输入javac回车”后提示“javac不是内部或外部命令
可能没有关系cmd，需要重新打开cmd命令，重新输入以上命令
原文地址：[Win7下JDK环境变量的设置](http://www.cnblogs.com/pxue/archive/2011/05/10/2042530.html)

#### 安装tomcat

Tomcat 服务器是一个免费的开放源代码的Web 应用服务器，属于轻量级应用服务器，在中小型系统和并发访问用户不是很多的场合下被普遍使用，是开发和调试JSP 程序的首选。对于一个初学者来说，可以这样认为，当在一台机器上配置好Apache 服务器，可利用它响应HTML（标准通用标记语言下的一个应用）页面的访问请求。实际上Tomcat 部分是Apache 服务器的扩展，但它是独立运行的，所以当你运行tomcat 时，它实际上作为一个与Apache 独立的进程单独运行的。

tomcat不需要安装直接修改环境变量即可，可在官网下载对应的版本[tomcat官网](http://tomcat.apache.org/) 
解压文化到相应的文件位置

##### 配置环境变量
1. 配置tomcat需要安装jdk，以上省略
2. 在系统变量里新建变量名：CATALINA_BASE；变量值：D:\tomcat\apache-tomcat-9.0.0.M9（后面是文件位置的绝对路径）
3. 在系统变量里新建变量名：CATALINA_HOME，变量值：D:\tomcat\apache-tomcat-9.0.0.M9（后面是文件位置的绝对路径）
4. 在系统变量里打开PATH，添加变量值：%CATALINA_HOME%\lib;%CATALINA_HOME%\bin
5. 打开cmd，进入tomcat下的bin目录，执行“service.bat install”  附：service卸载命令：service.bat remove
6. 或者打开cmd 在根目录直接运行startup命令，会启动服务
7. 测试安装是否成功，在浏览器打开，使用浏览器打开http://localhost:8080/，若成功打开则表示tomcat安装且运行成功

原文连接：
1. [windwos10上安装tomcat（详细步骤） ](http://blog.csdn.net/zhouzezhou/article/details/52450810)
2. [win8.1上安装tomcat](http://blog.csdn.net/chr23899/article/details/40400959)

