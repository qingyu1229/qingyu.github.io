---
layout: post
title:  Linux下编译安装OpenCV, 并使用java开发
category: OpenCV
date: 2014-10-13
---
---
现在要搞的一个事是在linux把eclipes下java开发openCV搞定。

##linux编译安装OpenCV
很简单参见官方文档：[点这里][1]

##Part1.下载OpenCV, 我用的是最新的openCV3.0

##Part2 安装cmake:
> sudo apt-get install cmake

##Part3 安装cmake图形画界面
> sudo apt-get install cmake-qt-gui

##Part4 编译安装openCV
> 
- 首先建个文件夹，一般叫build吧。然后终端运行cmake-gui打开图形界面。
- Browse Source找你的openCV解压目录， Browse Build找你刚才建的文件夹的目录， 然后点Configure，完事点Generate。
- 完成之后，进入build目录， 运行make， 完成后openCV就安装成功。

##Part5 安装openCV-java
这里也有个官方文档：[点这里][2]
具体安装教程参见这里：[这里][3]

##Part6 如何判断是否安装成功
以上操作结束后，build目录下的bin目录中会有一个openCV-300.jar的包，这样你就成功了。我因为用图形话工具cmake的，发现万事之后直接就有了这个包，因此省略了第5步

##Part7 配置Eclipse
参见这篇文章： [点这里][4]

  [1]: http://docs.opencv.org/trunk/doc/tutorials/introduction/linux_install/linux_install.html
  [2]: http://docs.opencv.org/doc/tutorials/introduction/desktop_java/java_dev_intro.html
  [3]: http://x-wei.github.io/linux%E4%B8%8B%E5%AE%89%E8%A3%85%E5%B9%B6%E4%BD%BF%E7%94%A8java%E5%BC%80%E5%8F%91opencv%E7%9A%84%E9%85%8D%E7%BD%AE.html
  [4]: http://exintopro.net/blog/2013/10/02/setting-up-eclipse-for-using-opencv-java-in-ubuntu/
