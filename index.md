---
layout: page
title: 从头到尾
tagline: 码农刘同学的新屋场
---
{% include JB/setup %}


<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
<p>
      <a href="http://weibo.com/nuxuil" class="btn btn-large" target="_blank">新浪微博</a>
      <a href="http://zhihu.com/people/liuxun" class="btn btn-large" target="_blank">知乎</a>
      <a href="http://www.douban.com/people/liu/" class="btn btn-large" target="_blank">豆瓣</a>
      <a href="http://dbd.im" class="btn btn-large" target="_blank">大笨蛋</a>
      <a href="http://liuxun.net" class="btn btn-large" target="_blank">老屋场</a>
</p>