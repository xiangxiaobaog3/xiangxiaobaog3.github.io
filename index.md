---
layout: page
title: Welcome to Xiangxiaobao's blog!
description: This is Xiangxiaobao's blog.I share coding,reading,music and some thoughts about life here.
keywords: Mac,iPhone,Apple,Code,Program,Github,Vim,Music,Reading,,音乐，编程，读书，阅读
tagline: --read & think
---
{% include JB/setup %}
    
## Posts List

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
