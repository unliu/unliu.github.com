---
layout: post
title: "firefox中，javascript的行为先后问题"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
在firefox中，Ctrl-S的功能是“网页另存为”。而我一直很想给blog实现这个功能：写日志时按Ctrl+S即可提交表单内容，同时（最关键的是）不弹出网页另存为的对话框。
要阻止“另存为”对话框，自然只能是在javascript中使用return false。而要实现提交表单功能，又必须捕获键盘事件Ctrl-S，使其有所执行。
我第一版的代码是：

`<body onkeydown="submitForm(event);return false;">`

结果发现文本框不能输入英文字符。显然的，它把所有的键盘输入都return false了。另据实际经验，return false写在函数判断里面是无用的。我想到在submitform函数里做一个“转发器”，专事将键盘输入的东西还原为字符写入到文本框内。先做测试，有第二版代码：

`<body onkeydown="test('我发送了表单，还把其它键盘输入转发了，耶。');return false;">`

结果发现，“Ctrl-S调出另存为对话框”这个行为几乎是优先于所有js函数调用和输出的。也就是说，只要return false前面有函数调用和输出，那对话框必然先被调出；而把函数调用和输出写在后面又显然无效。问题相当严重。幸好没有着急写“转发器”。
“[谷歌](http://www.google.com)”了一下，看到有人曰（[http://www.codingforums.com/showthread.php?t=69761](http://www.codingforums.com/showthread.php?t=69761)）：

> Any key combinations with special meanings to either the operating system or the browser are NOT passed to the web page and therefore cannot be handled using Javascript. To be able to process Ctrl-G in Javascript you would have to disable that option in your browser first. For it to work for your visitors they would have to disable it in their browser.


顿觉心灰意冷。但又确实知道[writely](http://www.writely.com/)已经实现了对Ctrl-S的“劫持”。遂坚定信心，多次尝试，终于得到正解：

`<body onkeydown="if(event.ctrlKey && event.keyCode==83){document.forms['write'].submit();return false;}">`

原来唯独表单提交这一动作可以赶在“另存为”框弹出之前完成。至此问题暂时解决。

方法缺陷是——如果把正解中onkeydown的值包装成一个函数调用，则return false无效。因此无法实现代码结构化，难以扩展快捷键操作的功能。

（不知道这篇帖子怎么会招来那么多 online poker 的spam留言，被迫关掉回复： `if(!empty($p_logid) && $p_logid!=185){//提交留言}）`