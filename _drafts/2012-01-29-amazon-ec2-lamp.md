---
layout: post
title: "亚马逊弹力云（EC2）之LAMP部署备忘"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
出于某些不可告人的目的，假期折腾了一把传说中的亚马逊“弹力云”（Amazon Elastic Compute Cloud，Amazon EC2）。与国内一般的“虚拟主机”或云平台不同的是，EC2提供的是基于[Xen](http://zh.wikipedia.org/wiki/Xen)的一个全功能的虚拟机，你可以任意选装操作系统和配置服务，搭建你想要的任何服务，甚至VPN。

折腾过程中参考了以下文章：
[Amazon EC2 Ubuntu折腾笔记](http://www.donchen.info/index.php/2011/06/amazon-ec2-ubuntu%E6%8A%98%E8%85%BE%E7%AC%94%E8%AE%B0/) [Amazon Web Service 雲端運算平台攻略](http://www.inside.com.tw/2010/11/08/free-aws-3) [Building EC2 Amazon Linux with LAMP](http://jonathanhui.com/building-ec2-amazon-linux-lamp) [Windows下如何用putty连接Amazon EC2实例图文教程](http://www.baidu.com.ru/archives/573.html)

一、初始配置

1. 注册、创建实例和选择系统镜像不再赘述。我选的是64位的 Amazon Linux 和 t1.micro 方案。
2. 以上步骤完成后，可在Elastic IPs里添加一个独立IP，但注意要将这个ip挂到一个实例上，否则据说有0.1美元/小时的收费
3. Security Groups 里开放以下端口：
    SSH：22 TCP
    HTTP：80 TCP
    HTTPS：443 TCP
    FTP：21 TCP
    62222-63333 用于支持FTP连接的被动模式（PASV），详见后文
4. 这个时候，操起Putty，挂上转换好的ppk文件，就可以登录主机了。注意登录名为：ec2-user，不需要密码。



二、LAMP配置
1. 更新系統
`# sudo yum update`
2. 安裝apache, php，mysql和vsftpd。
    # sudo yum install apache mysql php php-mysql mysql-server vsftpd


3. 具体配置备忘
- sudo vi /etc/php.ini，将short_open_tag = Off改为On，再增加一行 date.timezone = "Asia/Chongqing"，保证环境的兼容。
- sudo vi /etc/vsftpd/vsftpd.conf，把anonymous_enable=YES改为NO，在文件最后部分加上下面内容：
    pasv_enable=YES
    pasv_min_port=62222
    pasv_max_port=63333

这样，就可以用通常的PASV方式连接ftp。


4.启动服务
    # sudo service httpd start
    # sudo service mysqld start
    # sudo /etc/init.d/vsftpd start



这个时候，就可以sudo vi /var/www/html/index.php，写代码再:wq，用浏览器访问之前设定的Elastic IP，看看效果了。