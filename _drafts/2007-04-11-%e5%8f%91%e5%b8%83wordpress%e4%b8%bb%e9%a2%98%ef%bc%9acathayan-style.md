---
layout: post
title: "发布wordpress主题：cathayan-style"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
由来：
一直想找一个看起来最最没有个性，而且干净，而且单屏信息量充足、节约滚屏时间的主题。久觅不得，遂看上了[cathayan的blog](http://blog.cathayan.org/)，起了将其移植到wordpress平台的念头。

下载：
[本地下载](wp-content/uploads/2008/11/cathayan-style.zip)，或者到[Theme viewer下载](http://themes.wordpress.net/columns/2-columns/2534/cathayan-style/)。

安装：

1. 下载解压到wp-content/themes/ 。
2. 打开解压后目录里的压缩包 random-quotes-chinese.zip，解压里面的random-quotes-chinese.php到wp-content/plugins/ （然后可以删掉random-quotes-chinese.zip）。
3. 去wordpress后台启用模板"Cathayan Style"和插件"Random Quotes (Chinese)"。


两个问题：
- 字体大小：被迫使用px
本来觉得用像素值（px）设定字体大小，使IE用户没法调整字号，实在[不够人性化](http://jorux.com/archives/95-websites-of-china-need-to-rewrite-css/)。但在谷歌N遍，看完N篇文章之后，终于被迫放弃其它所有支持IE调整大小的设定方法，原因如下：
1. firefox和IE的默认字体大小不一样，然而用相对单位时，字体大小的差距会被放大，没有办法保证界面的大概的一致
2. 用normal,small,large,x-small...的定义方法，差距同样相当大（参考[http://blog.cathayan.org](http://blog.cathayan.org)在firefox和IE下的效果）
3. 在国内，绝大多数网站在IE下是不可调整字体大小的，因此绝大多数人已经事实上地失去了调整字体的习惯；只有对浏览体验比较敏感的人才会注意到字体调整功能；而——
4. 我相信，这样的朋友一定不会错过极度优秀、开放源码的[Firefox](http://www.mozilla.org.cn/)浏览器：）。（我一直使用，强烈推荐）


目前看到唯一不使用绝对字体大小而还过得去的模式是像Web4C一样，直接使用默认大小，在两种浏览器中分别显示为15和16像素--可惜这个大小显然不适合现在的cathayan-style。
- 用表格实现多行文字在容器里上下居中。本来cathayan 在Email里介绍了个非常牛的div实现方法
（[http://realazy.org/lab/div-valign/](http://realazy.org/lab/div-valign/)），可惜我人品有限，调试时冒出了一些短时间内搞不定的诡异问题，只好作罢。


版权：
设计是cathayan的（其授权是“Public domain都行吧"），里面的插件“Random Quotes (Chinese)"是（修改自）[xinple](http://xinple.org/)同学的（其授权是“没关系，随便发布 :) 加不加链接也无所谓的，能方便其他用户就好。"），呵呵，所以本Theme的版权是——[Public Domain](http://zh.wikipedia.org/wiki/%E5%85%AC%E6%9C%89%E9%A2%86%E5%9F%9F)（“公共财产”）。