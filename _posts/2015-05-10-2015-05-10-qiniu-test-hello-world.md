---
layout: post
title: "七牛云存储试用"
description: ""
category: 生活 , 技术
tags: [云存储,CDN,nephew]
---
{% include JB/setup %}
<script src="http://cdn.bootcss.com/jquery/1.11.3/jquery.js"></script>
<script src="http://cdn.bootcss.com/fancybox/2.1.5/jquery.fancybox.pack.js"></script>
<link href="http://cdn.bootcss.com/fancybox/2.1.5/jquery.fancybox.min.css" rel="stylesheet">
<link href="http://cdn.bootcss.com/bootstrap/3.3.4/css/bootstrap.min.css" rel="stylesheet">
<style>
	img {
		width:270px;
		height:270px;
	}
</style>
<script>
$(document).ready(function() {
    $('.fancybox').fancybox();
});
</script>

这两天申请了七牛云存储，并通过验证成了标准用户，想看看他家的cdn怎样。
随便翻了几张侄子的照片放到上面，写篇新功课来测试下，果然速度还不错，
本篇还用到了bootstrap的Grid system 和 facybox。

<kbd>These are my nephew's photos. :)</kbd>
<div class="container">
	<div class="row">
        <div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
			</a>
		</div>
		<div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_4.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_4.jpg">
			</a>
		</div>	
    </div>
	<div class="row">
        <div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_5.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_5.jpg">
			</a>
		</div>
		<div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_6.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_6.jpg">
			</a>
		</div>	
    </div>
	<div class="row">
        <div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_7.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_7.jpg">
			</a>
		</div>
		<div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_8.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_8.jpg">
			</a>
		</div>	
    </div>
	<div class="row">
        <div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_9.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_9.jpg">
			</a>
		</div>
		<div class="col-md-4">
			<a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_10.jpg" rel="gallery"  class="fancybox" title="">
			<img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_10.jpg">
			</a>
		</div>	
    </div>
</div>
