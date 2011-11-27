---
layout: post
title: Nike+ widget
---
{{ page.title }}
================

过年前买了个Nike+来做跑步的记录，买它的一个很重要的原因是[NickRunning][nike]网站提供一个很不错的控件。结果买来才发现
Nike+在2006年已经停止控件的开发和支持，当时承诺的很快的新功能到现在也没看到。不过看别人以前的还可以工作，只是
需要知道自己的id值。找了几个网页，发现登录后自己“目标“的url最后一个路径可能就是。试了一下果然可以，显示profile的效果：




<div>
     <embed width="200" height="200" align="middle" pluginspage="http://www.macromedia.com/go/getflashplayer" type="application/x-shockwave-flash" flashvars="id=1168827429&dateFormat=MM/DD/YY&region=cn&language=zh&locale=zh_us" allowscriptaccess="sameDomain" name="Nike+ Profile" bgcolor="#ffeeff" wmode="transparent" quality="high" src="http://nikeplus.nike.com/nikeplus/v1/swf/scrapablewidget/profile.swf">
</embed>
</div>



代码是：


          <embed width="200" height="200" align="middle"
                 pluginspage="http://www.macromedia.com/go/getflashplayer"
                 type="application/x-shockwave-flash" 
                 flashvars="id=1168827429&dateFormat=MM/DD/YY®ion=cn&language=zh&locale=zh_us" 
                 allowscriptaccess="sameDomain" name="Nike+ Profile" 
                 bgcolor="#ffeeff" wmode="transparent" 
                 quality="high" src="http://nikeplus.nike.com/nikeplus/v1/swf/scrapablewidget/profile.swf">


下一步要考虑怎么改样式放到blog里。

[nike]: http://nikerunning.nike.com
