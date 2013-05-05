---
layout: post
title: 更新了Scanty On GAE
---

appengine-tools的版本有很久没有更新了，今天把更新了的版本推上了GAE，加入了buzz更新。顺便还修正了原来的一个bug。为了让scanty跑在GAE上，dm-appengine替换了原来的Sequel作为ORM。在输出tag的时候有如下一段代码：


<!-- more -->

{% highlight ruby %}
def linked_tags
  tags ||= []
  ags.inject([]) do |accum, tag|
    accum << "<a href=\"/past/tags/#{tag}\">#{tag}</a>"
  end.join(" ")
end
{% endhighlight %}       


结果总是输出为空。后来发现dm是通过method-missing来帮助model访问数据的，这里的tags不应该是local
variable而是method。但是第一个语句导致ruby把tags解析为local
variable，这样总是得到一个空数组。把tags方法返回的结果clone一下然后使用就可以解决了。

ruby丰富（或者是复杂）的语法特性可以帮助写很多漂亮的代码，但是调试起来很头痛。你的代码拥有更高的抽象级别，对于你写代码的能力就有更高的要求。在jruby
on GAE的环境下更是麻烦。
