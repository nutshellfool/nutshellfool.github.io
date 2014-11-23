---
layout: post
title: "创建iOS静态Frameworks的步骤"
date: 2014-07-12 17:44:46 +0800
comments: true
categories: iOS，static frameworks，SDK
---
将共用代码lib化、重用，是代码管理的一种重要手段。  

废话少说，直奔主题。  
总的来说创建static framework 的方式有两种形式：  

1.	lib.a + .h(头文件) xCode 默认支持的工程方式。  
2.	同其他的内建系统frameworks一样的bundle。
	
首先说说第一种形式：
	
*	xCode内建支持项目类型
*	C、C++ 系lib工程的形态
*	头文件与库文件分离，引入工程时略显麻烦  

这种形态的工程我就不再啰嗦了，网上的教程已经很多了，Google一下就有很多（一定要用Google，度娘只会告诉你那个网站给度娘的广告出价最高 -- 对不起，不小心又黑百度了）。  
  
  
  
那好我们来重点说说后一种bundle形式的static frameworks：  
先来看看效果图：  
![static framework](/images/createframework/staticframeworks.png)  
在创建这个工程之前需要安装一个第三方的xCode插件：[iOS-Universal-Framework](https://github.com/kstenerud/iOS-Universal-Framework/)  
在这个例子里请安装 “Real Framework“ ：具体的安装步骤就是执行文件夹下的 install.sh shell脚本  
`$./install.sh`  

安装完成后重启xCode，static framework 工程就华丽的出现了。