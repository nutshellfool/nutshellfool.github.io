---
layout: post
title: "我的第一篇OctoPress博客"
date: 2014-02-27 10:07:21 +0800
comments: true
categories: 
---
***

经过一番折腾，终于把OctoPress成功部署在github上了。   
下面就把搭建过程集结成册，记录下来，方便日后使用。  
PS: 搭建的过程中参考了唐巧的这篇博客[象写程序一样写博客：搭建基于github的博客](http://blog.devtang.com/blog/2012/02/10/setup-blog-based-on-github/)   
   
***

###搭建环境
	Mac : OSX Mavericks 10.9.1  
	Ruby : ruby 2.0.0p247 (2013-06-27 revision 41674) [universal.x86_64-darwin13]
	Git : git version 1.8.3.4 (Apple Git-47) 
  
###首次搭建

####准备工作
首先需要安装一些必要的工具。这些内容在[OctoPress官网](http://octopress.org/docs/setup/) 上有详尽的说明。我只是把 OS Mavericks 10.9 下需要做的事情罗列一下。  
    
首先安装rvm  
安装：

{% codeblock %}  
sh -s stable < <(curl -s https://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer)
{% endcodeblock %}

设置classpath:  
shell为系统默认的情况（大多数）  
{% codeblock %}
echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # Load RVM function' >> ~/.bash_profilesource ~/.bash_profile{% endcodeblock %}
shell 为zsh  
{% codeblock %}
echo '[[ -s $HOME/.rvm/scripts/rvm ]] && source $HOME/.rvm/scripts/rvm' >> ~/.zshrcsource ~/.zshrc{% endcodeblock %}
####安装OctoPress  
先找一个你熟悉的文件路径，然后从github上将源码Clone下来：  
{% codeblock %}git clone git://github.com/imathis/octopress.git octopress
{% endcodeblock %}
进去看看   
{% codeblock %}cd octopress  
{% endcodeblock %}
然后安装依赖：   
{% codeblock %}sudo gem install bundler bundle install{% endcodeblock %} 

最后安装OctoPress 
{% codeblock %}   rake install{% endcodeblock %}
####配置    
主要是修改配置文件： __config.yml    
详细的配置项就不解释了，注释里写的很详细。    
需要注意的是：    
要把配置文件中的关于twitter信息删除，原因是GFW。
定制文件/source/_includes/custom/head.html 把google的自定义字体去掉，原因同上

####Github page托管服务    
怎么做？不详细说了，参见官网[Github pages](http://pages.github.com/)  

####创建第一篇博客试试  
{% codeblock %}
	rake new_post['My first blog']
	rake generate
	rake preview  
{% endcodeblock %}
然后在浏览器地址栏里输入  
http://localhost:4000/  
看到效果了么？Ok，试试下一步“部署”吧。  

####第一次部署


简单，看看官网的说明就好了[官网链接](http://octopress.org/docs/deploying/github/)  


####打完收工

提交成功后，再试试你的github page能不能如期显示。  
浏览器地址栏里输入：
 
	githubUserName.github.io  
	

***

本来文章写到这里就应该完成了，可是还是碰见问题了。

####Clone 已存在的博客Repository(第二次部署)
  
因为我常常是在公司和家里写博客，所以需要两套写博客的环境，因此需要在其他环境下Clone 这个托管在github上的博客Repository。怎么做呢？  
参见这篇博客：
[Setup an Existing Octopress Repository After Git Clone](http://weishi.github.io/blog/2013/07/24/setup-an-existing-octopress-repository-after-git-clone/)  

***

####其他的后话  
搭建好了环境只是万里长征的第一步，博客是用Markdown写的，所以要想写博客还是先学学Markdown的语法吧。  
先来个极其性感的简明教程： [Markdown简明教程](https://gitcafe.com/GitCafe/Help/wiki/Markdown-%E8%AF%AD%E6%B3%95%E9%80%9F%E6%9F%A5%E8%A1%A8)  
再来个完整版的: [Markdown 语法教程](http://wowubuntu.com/markdown/)

