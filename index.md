---
layout: page
title: Welcome to Jing0's blog!
description: This is Jing0's blog.I share coding,reading,music and some thoughts about life here.
keywords: iOS,Mac,iPhone,Apple,Code,Program,Eliza,C,Go,Github,Vim,Music,Reading,Jackie Kuo,音乐，编程，读书，阅读
tagline: --read & think
---
{% include JB/setup %}
    
## Posts List

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>