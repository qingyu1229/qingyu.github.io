---
layout: post
title: Java学习日志之Servlet
category: java
date: 2014-09-17
---

## Java学习日志之Servlet###什么是Servlet{% highlight java %}- 顾名思义Servlet就是服务器小程序，这个服务器可以是HTTP服务，也可以是邮件服务，也可以是FTP服务等等- java Web 应用中的请求-相应都是交给Servlet来完成- 原理图如下：   ！[servlet](http://www.blogjava.net/images/blogjava_net/fancydeepin/myself/servlet.png){% endhighlight %}###Servelt相关接口    **HttpServlet**类已经实现了Servlet接口所有方法，写Servlet时只需要即成这个类就行1. **doGet**与**doPost**:   - 这俩对应的就是HTTP报文中的GET与POST方法，也是最常用的两个。   - Get通常用于请求服务器发送某个资源。   - Post通常用来向服务器输入数据，通常用来支持HTML表单。   其他HTTP方法工作原理可参见**“HTTP权威指南”**   {% highlight java %}   对应的包与类：   javax.servlet.http.HttpServlet   Class HttpServlet   {% endhighlight %}   2. **request**与**response**
