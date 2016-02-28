---
layout: page
title: "Tags"
description: ""  
header-img: "img/semantic.jpg"  
---

## 目录与标签


###### 你可以通过这些标签来找到相应主题的文章，并且，所有文字的目录都被安放在这儿作为索引


<div id="post-list">
{% for tag in site.tags %}
<h2 id="{{ tag[0] }}">{{ tag[0] | capitalize }}</h2>
<ul class="post-list">
{% assign pages_list = tag[1] %}
{% for post in pages_list %}
{% if post.title != null %}
{% if group == null or group == post.group %}
<li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}<span class="entry-date"> ~ <time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%b %d, %Y" }}</time></a></li>
{% endif %}
{% endif %}
{% endfor %}
{% assign pages_list = nil %}
{% assign group = nil %}
</ul>
{% endfor %}
</div>

