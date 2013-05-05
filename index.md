---
layout: page
title: Try It Till Losing Enthusiasm
tagline: TITLE
---
{% include JB/setup %}


{% for post in site.posts %}
  <div>
  <h3><span>{{ post.date | date_to_string }}</span> &raquo;   <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
  </h3>

  <div>
    {{ post.content | split: '<!-- more -->' | first }}
  </div>
  </div>
 
{% endfor %}



