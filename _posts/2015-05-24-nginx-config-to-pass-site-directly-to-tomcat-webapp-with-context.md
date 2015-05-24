---
layout: post
title: "nginx 动态代理 tomcat"
description: "nginx 动态代理 tomcat，nginx 代理多个domain(网站) "
category: 技术
tags: [java,nginx,tomcat]
---
{% include JB/setup %}

由于本人平时除了搞搞Java还会倒腾PHP，所以希望在一台机器上同时部署两个webserver并同时监听80端口(http默认端口)。
下面我就以nginx和tomcat来做例子。实现nignx转发请求到tomcat上。
下面是我的配置：

	==tomcat端== 	
	在$TOMCAT_HOME/conf/server.xml的<Host appBase="webapps" autoDeploy="true" name="localhost" unpackWARs="true" xmlNamespaceAware="false" xmlValidation="false">里 添加一行 <Host name="youdomain.com" appBase="webapps"unpackWARs="true" autoDeploy="true">
	==nginx端==
	在nginx.cnf里添加一个server 
	server {
	  listen          80;
	  server_name     youdomain.com;
	  root            /usr/local/share/tomcat/webapps/family;
	
	  location / {
	        proxy_set_header X-Forwarded-Host $host;
	        proxy_set_header X-Forwarded-Server $host;
	        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	        proxy_pass http://127.0.0.1:8080/;
	  }
	}

配置好后，重启tomcat 和 nginx 访问domain(域名),就能看到tomcat里的项目了。

####这种方式适合通过多个tomcat实例来实现多个domain访问的情况。

还有一种可以放多个webapps的配置，如下：

	==tomcat端== 	
	在$TOMCAT_HOME/conf/server.xml中新建一个Host,
	<Host name="youdomain.com" appBase="webapps"
	                        unpackWARs="true" autoDeploy="true">
		<Alias>youdomain.com</Alias>
		<Context path="" docBase="family"></Context>
	</Host>
	==nginx端==
	在nginx.cnf里新建一个upstream和一个server 
	upstream youdomain.com {
	  server 127.0.0.1:8080;
	}
	server {
	  listen          80;
	  server_name     youdomain.com;
	
	
	  location / {
	        proxy_set_header X-Forwarded-Host $host;
	        proxy_set_header X-Forwarded-Server $host;
	        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	        proxy_pass http://youdomain.com;
	  }
	}

这样在tomcat端多建几个host,nginx端多建几个upstream就可以配置多个webapps了. 

####这种适合单个tomcat实例with多个webapps来实现多个domain访问的情况。
ps:个人倾向于第二种方式