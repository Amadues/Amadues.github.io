---
layout: archive
title: "文章"
date: 2018-1-03T23:11:36-04:00
modified:
excerpt: "学习笔记"
tags: []
image: 
  feature: 
  teaser:
---

以下就是我这个学期所归纳的可视化笔记

<div class="tiles">
{% for post in site.categories.infovis %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles 把所有categories 有 infovis 的列出来-->
