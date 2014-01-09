---
layout: post
title: "基于Ruby on Rails的Redmine在Windows下安装备忘"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
组里需要一个跟踪项目需求的系统，比照了JIRA(Confluence)、Trac、Redmine和国内的一大堆PHP平台的系统后，最终选择了基于Ruby的Redmine。不愧是Ruby社区的产物，界面清爽、配置便捷、逻辑明晰，甚是讨喜。现将安装配置步骤记录如下：

一、配置Ruby on Rails环境
-------------------

- 下载最新版的ruby1.8（1.8.7 p358，1.9 尚不被稳定版支持）和DEVELOPMENT KIT：[http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/)
- 分别安装之，安装ruby时将[将路径添加到环境变量path中]和[关联ruby文件]两个选项选中。
- 以管理员权限cmd进命令行，执行ruby -v检查版本。
- 如提示“‘ruby’不是内部或外部命令”，将 c:\Ruby187\bin\ 手动加入到系统PATH变量中（计算机->属性->高级系统设置->环境变量）。
- 解压devkit，在devkit目录中执行ruby dk.rb init，ruby dk.rb install（参考：[https://github.com/oneclick/rubyinstaller/wiki/development-kit](https://github.com/oneclick/rubyinstaller/wiki/development-kit)）
- 执行gem install rails --include-dependencies命令。安装后，执行rails -v检查。（我得到的提示是Rails 3.2.2）

二、安装Redmine
-----------

- 下载redmine1.3.2：[http://rubyforge.org/frs/?group_id=1850](http://rubyforge.org/frs/?group_id=1850). 参照[http://www.redmine.org/projects/redmine/wiki/RedmineInstall](http://www.redmine.org/projects/redmine/wiki/RedmineInstall) 建立数据库及用户。（注意编辑database.yml时，密码和冒号（:）之间要加空格，否则rake会出错）
- 解压redmine到devkit根目录下。进入redmine目录执行：
    gem install rake -v 1.1.0 #其它版本貌似有依赖问题
    gem install mysql
    rake generate_session_store
    gem update bundler #更新所有的gem，避免NOTE: Gem.source_index is deprecated 之类的告警

如果提示缺少libmysql.dll，下载[这个](http://instantrails.rubyforge.org/svn/trunk/InstantRails-win/InstantRails/mysql/bin/libmySQL.dll)到你的ruby/bin目录。
- 继续执行如下命令，配置初始数据库、启动服务：
    set RAILS_ENV=production
    rake db:migrate
    rake redmine:load_default_data #选择语言zh
    ruby script/server webrick -e production #启动webrick服务器



此时打开 [http://localhost:3000/](http://localhost:3000/) 就可以访问了。默认用户名：admin，密码：admin。

三、让Redmine自动运行
--------------

    gem install mongrel_service
    mongrel_rails service::install -N Redmine -c C:\devkit\redmine -p 3000 -e production
    sc config Redmine start= auto
四、安装截图插件
--------


这个插件只支持Webkit内核的浏览器，但貌似是唯一写明支持1.3.2版本的截图插件。地址：[http://www.redmine.org/plugins/javasript_screenshot](http://www.redmine.org/plugins/javasript_screenshot)
下载Patch for Windows：[http://gnuwin32.sourceforge.net/packages/patch.htm](http://gnuwin32.sourceforge.net/packages/patch.htm)
执行`patch.exe < _form.rhtml.patch`
（当然，由于版本问题，更靠谱的方式是找到c:\devkit\redmine\app\views\attachments\下的文件手动patch）

五、安装lightbox插件（直接显示附件图片）
------------------------


这个插件的遗憾是在Chrome下有bug，能显示缩略图，但不能以lightbox方式显示大图（里面用到的js库是压缩过的，还不好手改）。地址：[http://www.redmine.org/plugins/redmine_lightbox](http://www.redmine.org/plugins/redmine_lightbox)
注意：放到插件目录后须手动将目录名改为redmine_lightbox，否则会出错。

参考链接：
-----

[http://www.redmine.org/projects/redmine/wiki/RedmineInstall](http://www.redmine.org/projects/redmine/wiki/RedmineInstall) [http://www.cnblogs.com/liuxiaori/archive/2011/07/09/2101781.html](http://www.cnblogs.com/liuxiaori/archive/2011/07/09/2101781.html) [http://wenku.baidu.com/view/20c95b0bf78a6529647d5337.html](http://wenku.baidu.com/view/20c95b0bf78a6529647d5337.html)