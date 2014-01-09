---
layout: post
title: "我的xubuntu linux生活（持续更新）"
description: ""
category: ""
tags: []
---
{% include JB/setup %}
前言：
xubuntu linux是什么？简单说来，这是软件世界的一种共产主义理想。我跟计算机专业没有瓜葛，只因为成天想着等田亩均贫富劫富济贫，是一共产分子，恰好又有点理想主义，所以冲锋在前，加入了引领革命的第一集团军（小知识链接：[xubuntu](http://www.surf-anon.com/index.php?__script_get_form=aHR0cDovL3poLndpa2lwZWRpYS5vcmcvd2lraS9TcGVjaWFsOlNlYXJjaA%253D%253D&search=xubuntu&go=%E8%BD%AC%E5%88%B0)，[linux](http://www.surf-anon.com/index.php?__script_get_form=aHR0cDovL3poLndpa2lwZWRpYS5vcmcvd2lraS9TcGVjaWFsOlNlYXJjaA%253D%253D&search=linux&go=%E8%BD%AC%E5%88%B0) ，[自由软件](http://www.gnu.org/philosophy/free-sw.cn.html)）。

而一段时间后，我发现革命形势不是小好，也不是中好，而是一片大好。这让我有了更高的革命觉悟。同志们，要创造人类的幸福，全靠我们自己。发这篇文章，就是希望全世界无产者团结起来，咱们把旧世界打个落花流水，早点儿建立英特纳雄耐尔的新社会。

正文：

> 【动作：上网；工具：firefox,lumaqq,gaim】firefox。用Sage扩展开始读订阅的blog和各种网站论坛的新文章，在地址栏按g回车打开我的邮箱，再有空闲，用搜索栏google一会儿。发现好内容，选定，拉进ScrapBook扩展里的相应目录。（tip:配以web developer扩展，可以减少许多浏览阻碍）
> QQ自然是lumaqq，和win下的qq差不多，遗憾是不能传文件(传文件用myspace.grids.cn吧)。gaim可以用来登录msn，gtalk和irc聊天室。
> 
> 【动作：学习科学文化知识；工具：freemind,zim,OO,foxit,stardict等等】把ScrapBook里收来的资料/书上看到的东西整理到freemind里，成为一张张思维导图。不可分割的文章启动zim桌面维基，写上标题，Ctrl-L，贴进去；再在freemind里做一个链接到这篇文章。
> Word/Excel文档：启动OO，看起来排版有点偏差，但基本凑合。
> PDF，一般的用evince启动快些，需要标注笔记的使用wine+foxit，效果不错。
> 金山词霸替代：stardict。目前版本可以加载金山词霸的所有词典库。支持即时搜索和真人发音，功能完整。
> 
> 【动作：写日记；工具：zim】打开zim，按Alt-D，即生成当前日期的页，开始书写。
> 
> 【动作：听音乐；工具：bmp】启动bmp，播放列表一如昨日。操作和win下常见的音乐播放器没有什么差别。
> 
> 【动作：看电影；工具：mplayer】有了解码器的mplayer各种视频格式通吃，外挂字幕也没有问题；快捷键功能比暴风影音强大，做调整时不必切出全屏，用起来更顺手。
> 
> 【动作：下电影；工具：amule】某些电影非法拷贝的诱惑让人无法拒绝，amule是最佳犯罪工具。amule就是emule的linux版，功能不缺，速度不减，有时速度仿佛还快些。
> 
> 【动作：做网页；工具：nvu,bluefish,scite,geany,gimp,】nvu是所见即所得的编辑软件，不过功能自然比不上399美刀的dreamweaver；学学html和css吧，bluefish,scite和geany这些文本编辑器都很易用。gimp功能据说直逼售价$649的photoshop，只是易用性似乎差点。
> 
> 【动作：获取数码相机照片；工具：f-spot】f-spot内置支持的数码相机机型列表可以用“一望无际”来形容，获取、组织、调整照片的功能也接近商业软件。
> 
> 【动作：开发； 工具：eclipse】成熟的、强大的、易用的真正的IDE。写php配上[PHPeclipse](http://www.phpeclipse.de)，简直像用Zend一样。（当然，如果你舍得花钱或者勇于不花钱的话，Zend也有linux版）
> -----------------------------------------
> **系统管理相关**
> 
> 【安装】体验过这么轻松的系统安装么？把光盘塞进去，几分钟后，一个完整的xubuntu系统立即展现在你的面前。当然，这只是livecd的系统，点击桌面图标开始正式安装，然后可以一边上网一边装系统。15分钟系统装完，提示重启，点OK，收工，常用的软件都自动装好了。
> 
> 【装卸软件】突然需要一个录音软件，怎么办呢？打开终端，输入ai audacity回车，几分钟内软件从下载到安装自动完成，即可使用。卸载同样简单：ar audacity。（我给sudo apt-get install/remove配置了缩写为ai/ar）
> 
> 【开启ntfs分区读写】安装炙手可热的ntfs-3g，可使ntfs分区支持写入，且读写性能绝佳。xubuntu的文件管理器是thunar，操作ntfs-3g分区十分稳定。再也不用为双系统共存时空间的分配伤脑筋了。
> 
> 【双系统共享firefox配置与数据】firefox是一号常用软件。安装Google Browser Sync，就可以在windows和linux之间保持firefox的书签、cookies、密码存储数据等等各种状态的一致。至于Scrapbook，只需要双边把数据目录设在同一位置就行了。
> -----------------------------------------
> **初步总结**1. ubuntu的文档很详细，扫除了大量障碍。
> 2. ubuntu的论坛发展得也不错。
> 3. xfce桌面环境在我的T30上的确有优势，比如gimp的启动速度，与gnome环境相比几乎有几倍的提升。
> 4. 借用[这篇blog文](http://blog.csdn.net/group/raptor/content366901.aspx)的说法，“（尝试xubuntu）最大的体会就是：现在的Linux可用性实在是很高了，大部分工作都已经可以在Linux下完成，不需要Windows也没有问题。”


后记：
自从发现了Eclipse，一切个人电脑使用(做项目/学习/娱乐..)就全是在xubuntu下进行了。离开Windows的日子，感觉还不错。:-)

我用freemind做了一些使用经验的记录(即时记录比较混乱，有空再认真整理(-:)。这里提供[下载](http://liuxun.googlepages.com/my_xubuntu_linux.mm)和[网页浏览](http://liuxun.yi.org/html/my_xubuntu_linux.html)。希望对革命同道有用。

(最后更新:2006.10.20)