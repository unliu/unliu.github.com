---
layout: page
title: 你好呀~
tagline: 这里是老刘同学的练习场
---
{% include JB/setup %}

## 编码问题

如果你在文档里写入了中文字符，可能会导致运行 `jekyll serve` 时提示：

    Liquid Exception: invalid byte sequence in GB2312 in index.md

这种情况，只需要在 `_config.yml` 文件里加一句 `encoding: UTF-8` 就可以了。


## 自动刷新

执行

    jekyll serve --watch

即可自动刷新，不用每次改东西都重启 jekyll 服务看效果了。

##文档

<!-- 回头把下面这些删了去 --> 

读 [Jekyll Quick Start](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)

Complete usage and documentation available at: [Jekyll Bootstrap](http://jekyllbootstrap.com)

## Update Author Attributes

In `_config.yml` remember to specify your own data:
    
    title : My Blog =)
    
    author :
      name : Name Lastname
      email : blah@email.test
      github : username
      twitter : username

The theme should reference these variables whenever needed.
    
## Sample Posts

This blog contains sample posts which help stage pages and blog data.
When you don't need the samples anymore just delete the `_posts/core-samples` folder.

    $ rm -rf _posts/core-samples

Here's a sample "posts list".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## To-Do

This theme is still unfinished. If you'd like to be added as a contributor, [please fork](http://github.com/plusjade/jekyll-bootstrap)!
We need to clean up the themes, make theme usage guides with theme-specific markup examples.


