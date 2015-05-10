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
<table class="table table-striped table-bordered table-hover table-condensed">
    <!-- 颜色-->
    <tbody>
    <tr class="active text-center">
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
    </tr>
    <tr class="info text-center">
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
    </tr>
    <tr class="success text-center">
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
    </tr>
    <tr class="danger text-center">
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
        <td>
            <a href="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg" rel="gallery"  class="fancybox" title="">
                <img src="http://7xizaz.com1.z0.glb.clouddn.com/nephew_3.jpg">
            </a>
        </td>
    </tr>
    </tbody>
</table>
