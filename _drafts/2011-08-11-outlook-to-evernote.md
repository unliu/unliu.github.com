---
layout: post
title: "从Outlook便笺导出到Evernote的脚本"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
终于决定从Palm平台迁移到Android，memo中的数百条备忘遂成了难题。思前想后，看来只能走memo——Outlook便笺——Evernote的曲线救国战略。

而实际上Outlook转Evernote也不易找到现成的工具，几经选择关键词，才搜到如下的VB脚本：

[http://www.fourteenminutes.com/code/outlook2evernote/](http://www.fourteenminutes.com/code/outlook2evernote/)

此脚本的最大问题是不支持中文。大约因为vbs不便直接转换为Unicode，便笺里非基本英文或数字的字符都被转成ASCII码表示，得到的enex文件以ANSI方式保存。此时如果内文里有中文，由于某些兼容不良的未知问题，会导致报错。

Evernote的enex格式其实是认UTF-8的。因此我修改了代码，除去了对字符的ASCII转换，排除了报错问题。这样生成的enex文件显然不能直接用，需要用Editplus之类的编辑器打开，**手动另存成UTF-8编码，方可导入到Evernote**。

此外，原脚本不支持分类导出，所以顺便加了一项，将Outlook里的分类识别为Evernote里的标签。

修正版脚本下载地址：[http://vdisk.weibo.com/s/wcTu](http://vdisk.weibo.com/s/wcTu) ，解压后按原网站指示运行即可。