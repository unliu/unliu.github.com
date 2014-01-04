---
layout: post
title: "PHP 的包管理器：Composer"
description: ""
category: ""
tags: []
---
{% include JB/setup %}

##Composer 之初见

这个包管理器感觉还是很不错的。它的方式很简单：在`composer.json`里面定义好`require`关键字，就设定了你当前包依赖（也就是需要自动下载）的其它包。运行 `composer install`，即可自动安装`composer.json`定义好的特定版本的包了。

而这种`require`关系是多级的，可以无限延伸的；`require`时又设定了版本号范围。这就使得 Composer 成为了一个正港的包管理工具啦。

##如何安装

参考 [官方文档](http://getcomposer.org/doc/00-intro.md)

	$ curl -sS https://getcomposer.org/installer | php
	$ mv composer.phar /usr/local/bin/composer
	
或者有 homebrew 的话，更简单：

	brew tap josegonzalez/homebrew-php
	brew install josegonzalez/php/composer
	
然后，只要设定好了 `composer.json`，在目标目录直接使用`composer install`命令即可。这个命令会把包下载到 `vendor/vendorname/packagename` 目录中（如果 vendor 目录不存在，会自动创建）。

##我常用的包

具体的可以在 [https://packagist.org/](https://packagist.org/) 上看。我用到的包括：

* coffeescript/coffeescript
* leafo/lessphp
* twitter/bootstrap
* redis?
* mssql?

安装以上包以后，在 base 控制器里加一句`require 'vendor/autoload.php';`，即可进入想用啥包用啥包，物质极大丰富的共产主义时代了！