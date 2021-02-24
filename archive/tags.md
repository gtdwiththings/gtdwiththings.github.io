---
layout: default
title: Archive
permalink: /archive/tags
---

<div class="archive-menu">
	<span class="archive-inactive"><a href="/archive/" title="all">all posts</a></span>
	<span class="archive-active"><a href="/archive/tags" title="tags">by tag</a></span>
</div>	


{%- assign sortedTags = site.tags | sort -%}

<div class="tag-list">
{% for tag in sortedTags %}
<a href="#{{tag[0]}}">{{ tag[0] }}&nbsp;({{ tag[1] | size }})</a>
{% endfor %}

</div>

{% for tag in sortedTags %}

<section class="posts-by-tag">

<h2 id="{{ tag[0] }}">{{ tag[0] }}</h2>

{% for post in tag[1] %}
	{% include blog-listing.html %}
	<br />
{% endfor %}

<hr />
{% endfor %}