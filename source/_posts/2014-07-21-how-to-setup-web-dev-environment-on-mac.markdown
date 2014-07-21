---
layout: post
title: "如何在Mac上搭建Web开发环境"
date: 2014-07-21 16:16:18 +0800
comments: true
categories: Mac,Web,开发环境
---

**本机环境：**

	OS：  Mac 10.9.4
	

**目标环境：**

	PHP + MySQL + nginx
	
	
*因为这几个环境之间相互独立，所以安装搭建的顺序可以很随意*  

其实Mac 已然成为目前主流的开发操作系统，所以这些主流的开发环境的搭建也是很轻易的就可以Google来。  
废话了这么多，说点实在的干货：

##* PHP
系统内建支持的环境，无需安装。

##* nginx
  

怎样在mac 上安装 nginx？  

-- brew  

如果你的 mac 上已经安装过了brew， 那么
`brew install nginx` 就可以解决问题  

啥？ brew没有安装？   
没问题， 在上一个命令之前执行  
`ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"`  
就可以。  

##* MySQL
MySQL是提供DMG格式的安装包的，这一点可以赞一下。  
官网的下载地址：  
[http://dev.mysql.com/downloads/mysql/](http://dev.mysql.com/downloads/mysql/)   
选择 “Mac OS X 10.7 (x86, 64-bit), DMG Archive”， 点击 Download开始。  
剩下的事情就简单了，按照Mac下安装软件的步骤就可以完成。  
如果你是命令行控，那么强烈建议你添加这两个 alias：  
	
	alias mysql=/usr/local/mysql/bin/mysql
	alias mysqladmin=/usr/local/mysql/bin/mysqladmin
	
如果需要更详细的细节，请访问： [Mac OS X 安装mysql过程](http://www.wkii.org/mac-os-x-install-mysql-dm.html)

好了，剩下的事情就需要你的发挥了。  
Ok, that's all, enjoy it.