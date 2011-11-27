---
layout: post
title: iPad上Safari的Bookmarklet
---

{{ page.title }}
================

 
经常用ipad阅读web的内容话会很希望能记录下来以后回顾或者分享给别人，如果不安装应用作为safari的插件或者换个浏览器挺困难的。
昨天无意中发现IPad的Safari浏览器是能够支持bookmarklet的，这样很多常用的应用就可以无缝的迁移到IPad上了。


首先先创任意的一个书签：


![create][create]

 然后在书签栏里修改刚才创建的书签


![update][update]

修改标题，把所需的bookmarklet脚本替换到地址栏


![replace][replace]


之后只要打开页面后点相应的书签就可以分享记录了，非常方便。


[create]: https://www.wuala.com/en/api/preview/tdsparrow/public_sync/images/2011-05-02/IMG_0001.PNG
[update]: https://www.wuala.com/en/api/preview/tdsparrow/public_sync/images/2011-05-02/IMG_0002.PNG
[replace]: https://www.wuala.com/en/api/preview/tdsparrow/public_sync/images/2011-05-02/IMG_0003.PNG

下面是我添加的三个服务的bookmarklet脚本，其他服务应该可以很容易在各自的网站找到：


Google Reader Note:

          javascript:var%20b=document.body;var%20GR________bookmarklet_domain='https://www.google.com';if(b&&!document.xmlVersion){void(z=document.createElement('script'));void(z.src='https://www.google.com/reader/ui/link-bookmarklet.js');void(b.appendChild(z));}else{}

readlilater:

          javascript:(function(){ISRIL_H='3481';ISRIL_SCRIPT=document.createElement('SCRIPT');ISRIL_SCRIPT.type='text/javascript';ISRIL_SCRIPT.src='http://readitlaterlist.com/b/r.js';document.getElementsByTagName('head')[0].appendChild(ISRIL_SCRIPT)})();

evernote:

          javascript:(function(){EN_CLIP_HOST='http://www.evernote.com';try{var%20x=document.createElement('SCRIPT');x.type='text/javascript';x.src=EN_CLIP_HOST+'/public/bookmarkClipper.js?'+(new%20Date().getTime()/100000);document.getElementsByTagName('head')[0].appendChild(x);}catch(e){location.href=EN_CLIP_HOST+'/clip.action?url='+encodeURIComponent(location.href)+'&title='+encodeURIComponent(document.title);}})();

