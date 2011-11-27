---
layout: post
title: Blog搬家到GAE
---


{{ page.title }}
================

这周在[GAE][gae]上架好了一个简单的blog，从此可以摆脱自己二奶机上的[typo][]了。也许将来可以多写一点。
[gae]: http://appengine.google.com
[typo]: http://typosphere.org


这个blog是基于[scanty][]的，稍加[改动][git]后使这个[sinatra][] app可以跑在[GAE][gae]上。[sinatra][]的简洁挺适合我入门web的，而[GAE][gae]也可以保证服务的可靠，以前二奶机总是有这那的问题（不过好像GAE上应用启动的时间挺长的）。
[scanty]: http://github.com/adamwiggins/scanty
[git]: http://github.com/tdsparrow/scanty
[sinatra]: http://www.sinatrarb.com/

[GAE][gae]并没有直接提供ruby的支持，但去年提供java的版本后很多人开始捣鼓各种有java解释器的脚本语言，web开发很流行的ruby自然不在话下。现在开发一个可以部署到[GAE][gae]的ruby应用已经变得很简单了，以现在这个简单的blog为例：  

*  安装[GAE][gae]开发需要的

         gem install google-appengine
    	 gem install 
         gem install 
         gem install dm-appengine

其中[google-appengine]包含了[GAE][gae]的SDK以及相应最基本的jruby环境和rack。warbler是帮助将ruby的文件打包到WAR包，bundler08则是帮助将app依赖的库导出到app的路径下，方便warbler打包，dm-appengine 是datamapper的datastore的adapter。

* 下载[scanty][]的代码

        git clone http://github.com/adamwiggins/scanty.git
        

* 启动[GAE][gae]应用

        dev_appserver.rb

* 修改scanty  
    1. Gemfile需要打包的依赖  
    2. 修改lib/post.rb中model的代码，更换为使用dm-appengine  

* 创建GAE应用并上传

