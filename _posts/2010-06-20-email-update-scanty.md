---
layout: post
title: Email更新scanty 
---

{{ page.title }}
================

Scanty只有一个简陋的编辑后台，通过桌面发布很多时候是个不错的选择。可以选择其它第三方的工具如live writer，或者是通过邮件。
gmail的功能也足够强大，甚至自动就作了备份。更重要的是[GAE][gae]本身提供了很好的邮件支持，花一点时间今天给[Scanty Over GAE][git]添加了一个简陋的邮件发布通道。

中间碰到了[google-appengine]的一个陷阱，appcfg.rb每次都会检查几个配置文件的时间戳。一旦改变了就会重置，而默认的配置没有启用任何服务。修改了配之后需要更新时间戳记录：

	require 'rubygems'
	require 'appengine-tools/appcfg'

	path_to_app = ARGV.shift

	app = AppEngine::Admin::Application.new(File.expand_path(path_to_app))

	yaml = {
	     :config_ru => File.stat(app.config_ru).mtime,
	     :aeweb_xml => File.stat(app.aeweb_xml).mtime,
	     :web_xml => File.stat(app.web_xml).mtime
	}
	
	open(app.build_status, 'w') { |f| YAML.dump(yaml, f) }


[gae]:http://code.google.com/intl/en/appengine/docs/java/mail/receiving.html
[git]: http://github.com/tdsparrow/scanty
[google-appengine]:http://code.google.com/p/appengine-jruby/wiki/GettingStarted
