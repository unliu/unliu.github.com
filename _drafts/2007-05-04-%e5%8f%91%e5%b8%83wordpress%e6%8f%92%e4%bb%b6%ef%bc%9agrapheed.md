---
layout: post
title: "发布wordpress插件：Grapheed"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
我也不知道这算不算严格意义上的“插件”，因为它暂时没有办法用wordpress的“插件管理器”来管理：）

其实是[N久以前在校内发过](http://blog.xiaonei.com/GetEntry.do?id=637856)的老东西。现在改成的代码，略做细微修改就可以用于所有blog程序，只要空间支持php，而且有iconv和gd函数库。

	Plugin Name: Grapheed
	Plugin URI: http://blog.liuxun.net/?p=22
	Description: 可以将http://your-blog-url/wp-grapheed.php当作图片引用，在论坛签名档或xiaonei.com涂鸦板上显示自己的最新网志
	Version: 1.0
	Date: 2007/05/04
	Author: 刘寻
	Author URI: http://liuxun.net
	
	=== 安装步骤 ===
	1.从 http://www.ugia.cn/?p=82 下载点阵字库包（fontfun.rar），将包里的simsun12.fon上传至wordpress根目录（simsun是非自由字体，请自行解决版权问题）
	2.将 wp-grapheed.php 上传至wordpress根目录。即可使用。
	
	=== 版权声明 ===
	本程序部分代码（详见注释）参考自ugia.cn，版权属于ugia.cn
	
	其余部分，放弃所有版权，可以自由使用

[点这里下载](http://laoliu-wordpress.stor.sinaapp.com/uploads/2007/05/wp-grapheed.zip "Grapheed")