---
layout: post
title: "how to create maven project with templates"
description: ""
category: 技术
tags: [java,maven]
---
{% include JB/setup %}

最近一年一直搞的php，想想之前的Java知识丢了好多，有点不甘心，于是乎复习下之前的知识，用springmvc+mybatis搭建项目摆弄摆弄，项目管理工具用的是maven,说下怎么用maven从无到有的常见一个java web 项目。
之前一般都会用maven创建一个空的java web项目 通过以下命令

	mvn archetype:create -DgroupId=com.taijia.web -DartifactId=spmvc -DpackageName=com.taijia.web -DarchetypeArtifactId=maven-archetype-webapp

可是要想搭建springmvc+mybatis的框架的项目还需要一步一步的自己搭建，要是maven能把框架搭建的工作也做了就好了，网上搜搜后，发现还真可以。
见https://github.com/sivaprasadreddy/maven-archetype-templates和http://www.luckyryan.com/2013/02/15/create-maven-archetype-from-existing-project/这两篇文章，按照上面步骤试了下是可以的。

	[root@taijia-centos family]#  mvn archetype:generate -DarchetypeCatalog=local
	[INFO] Scanning for projects...
	[INFO]                                                                         
	[INFO] ------------------------------------------------------------------------
	[INFO] Building Maven Stub Project (No POM) 1
	[INFO] ------------------------------------------------------------------------
	[INFO] 
	[INFO] >>> maven-archetype-plugin:2.3:generate (default-cli) > generate-sources @ standalone-pom >>>
	[INFO] 
	[INFO] <<< maven-archetype-plugin:2.3:generate (default-cli) < generate-sources @ standalone-pom <<<
	[INFO] 
	[INFO] --- maven-archetype-plugin:2.3:generate (default-cli) @ standalone-pom ---
	[INFO] Generating project in Interactive mode
	[INFO] No archetype defined. Using maven-archetype-quickstart (org.apache.maven.archetypes:maven-archetype-quickstart:1.0)
	Choose archetype:
	1: local -> com.sivalabs.maven.archetypes:sivalabs-quickstart-archetypes-archetype (sivalabs-quickstart-archetypes-archetype)
	2: local -> com.sivalabs.maven.archetypes:quickstart-springmvc-mybatis-archetype (A Maven project using SpringMVC 3.1.x, MyBatis, jQuery and Log4j/Logback configuration.)
	Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): : 2
	[INFO] Using property: groupId = com.tangtaijia
	[INFO] Using property: artifactId = basic
	[INFO] Using property: version = 1.0-SNAPSHOT
	[INFO] Using property: package = com.tangtaijia
	Confirm properties configuration:
	groupId: com.tangtaijia
	artifactId: basic
	version: 1.0-SNAPSHOT
	package: com.tangtaijia
	 Y: : Y
	[INFO] ----------------------------------------------------------------------------
	[INFO] Using following parameters for creating project from Archetype: quickstart-springmvc-mybatis-archetype:0.0.1
	[INFO] ----------------------------------------------------------------------------
	[INFO] Parameter: groupId, Value: com.tangtaijia
	[INFO] Parameter: artifactId, Value: basic
	[INFO] Parameter: version, Value: 1.0-SNAPSHOT
	[INFO] Parameter: package, Value: com.tangtaijia
	[INFO] Parameter: packageInPathFormat, Value: com/tangtaijia
	[INFO] Parameter: package, Value: com.tangtaijia
	[INFO] Parameter: version, Value: 1.0-SNAPSHOT
	[INFO] Parameter: groupId, Value: com.tangtaijia
	[INFO] Parameter: artifactId, Value: basic
	[INFO] project created from Archetype in dir: /home/taijia/workspaces/family/basic
	[INFO] ------------------------------------------------------------------------
	[INFO] BUILD SUCCESS
	[INFO] ------------------------------------------------------------------------
	[INFO] Total time: 17.297 s
	[INFO] Finished at: 2015-05-03T18:19:33+08:00
	[INFO] Final Memory: 10M/25M
	[INFO] ------------------------------------------------------------------------