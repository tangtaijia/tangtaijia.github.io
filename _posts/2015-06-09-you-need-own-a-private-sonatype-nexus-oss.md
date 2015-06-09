---
layout: post
title: "搭建一个私人sonatype nexus的必要性"
description: ""
category: 技术
tags: [maven,java]
---
{% include JB/setup %}

啥也不说，看个对比先：

	[INFO] BUILD SUCCESS
	[INFO] ------------------------------------------------------------------------
	[INFO] Total time: 24:00 min
	[INFO] Finished at: 2015-05-31T18:16:04+08:00
	[INFO] Final Memory: 8M/40M
	[INFO] ------------------------------------------------------------------------

#####某国内公共 nexus的速度

	[INFO] BUILD SUCCESS
	[INFO] ------------------------------------------------------------------------
	[INFO] Total time: 03:25 min
	[INFO] Finished at: 2015-05-31T18:22:01+08:00
	[INFO] Final Memory: 8M/41M
	[INFO] ------------------------------------------------------------------------

#####个人 nexus的速度

这是对我的一个springmvc+mybatis的一个小项目的maven测试，每次mvn clean install 之前我都是把repository里的文件夹清空了，重新下载jar包的，速度确实差了不少，6、7倍。

用过maven我们都知道，默认的中央库是[http://repo1.maven.org/maven2/](http://repo1.maven.org/maven2/)，这是国外的，生活在国内，那速度简直不能忍。国内的库实际上也有，比如oschina(ps:良心)家的还不错。可惜毕竟还是公共的，每天多少人在用，有时很慢，不稳定，可想而知。所以想要一个稳定快速的maven库，我们还是最好自己搭建一个吧。可以搭建在本地，如果自己有vps的话，也可以在上面搭建一个。最好是国外的vps，因为搭建在上面的nexus下jar包会比国内的服务器快很多。这样还可以发挥下雷锋的精神带别人用用嘛，特别是可以给自己的团队用用。具体搭建方式可以参考[官方文档](http://books.sonatype.com/nexus-book/reference/prerequisites.html)。

我的就是自己的vps搭建的nexus,vps是东京节点的aws，ping 值稳定在200ms左右，家里带宽是移动10M。