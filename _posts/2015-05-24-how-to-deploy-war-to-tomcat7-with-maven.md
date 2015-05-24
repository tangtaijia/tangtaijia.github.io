---
layout: post
title: "通过maven命令部署项目到tomcat"
description: ""
category: 技术
tags: [maven,tomcat]
---
{% include JB/setup %}

平时做做项目，无论是本地打包还是远程打包，都会先maven install ，再到target/下找到相应的war包，cp到 $TOMCAT_HOME/webapps/下，再重新启动tomcat。

总觉得这样，每次都要做这种重复工作很无聊，作为一个合格的IT人士，不能在这种事情上浪费时间，于是想到了maven的tomcat插件，[Tomcat Maven Plugin](http://tomcat.apache.org/maven-plugin-2.0/tomcat7-maven-plugin/ "走你少年"),由于本人本地和vps用的是tomcat7,所以就用7做例子，其实tomcat6也差不多，除了一小点区别。

下面我来介绍下，怎么通过Tomcat Maven Plugin 来命令式，一键部署webapp,到本机（ps:远程也行，不过一般不会这么干，除了你和扫洞大侠是好朋友）。

###部署到本地tomcat
在pom.xml中加上Tomcat Maven Plugin

	<plugin>
	    <groupId>org.apache.tomcat.maven</groupId>
	    <artifactId>tomcat7-maven-plugin</artifactId>
	    <version>2.1</version>
	    <configuration>
	        <url>http://localhost:8080/manager/text</url>
	        <username>admin</username>
	        <password>admin</password>
	    </configuration>
	</plugin>

注意：
  tomcat7和tomcat8的url写http://localhost:8080/manager/text,命令是mvn tomcat7:xxx
  tomcat6的url写http://localhost:8080/manager/ , 命令是mvn tomcat6:xxx

还要在$TOMCAT_HOME/conf/tomcat-user.xml设置下username,password.

	<role rolename="manager-script"/>
	<user username="admin" password="admin" roles="manager-script"/>

注意：两处的username,password要一致

####命令介绍

	mvn tomcat7:deploy # 部署
	mvn tomcat7:undeploy # 移除部署
	mvn tomcat7:redeploy # 重新部署 

###把username、password独立出来
在多人协作开发的情况下，把username和password写死到pom.xml的做法，不太灵活。最基本的，你不会希望其他人看到你的username和password，就算你不介意，别人的username和password也可能跟你的不一样。

其实通过在$M2_HOME/conf/settings.xml里面配置，maven能做到每个人都保存各自的username和password的。

在$M2_HOME/conf/settings.xml配置如下信息：

	<server>
	    <id>tomcat-localhost</id>
	    <username>admin</username>
	    <password>admin</password>
	</server>

这样可以删除pom.xml中的username、password，修改成如下

	<plugin>
	    <groupId>org.apache.tomcat.maven</groupId>
	    <artifactId>tomcat7-maven-plugin</artifactId>
	    <configuration>
	        <server>tomcat-localhost</server>
	        <url>http://localhost:8080/manager/text</url>
	    </configuration>
	</plugin>
