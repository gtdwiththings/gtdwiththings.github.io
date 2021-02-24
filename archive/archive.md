---
layout: default
title: Archive
permalink: /archive/
---

<div class="archive-menu">
	<span class="archive-active"><a href="/archive/" title="all">all posts</a></span>
	<span class="archive-inactive"><a href="/archive/tags" title="tags">by tag</a></span>
</div>	

{% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
  <h1>{{ year.name }}</h1>
    
    {% for post in year.items %}

<div class="archive-list">
	&nbsp;&nbsp;<span id="title" markdown="0"><a href="{{ post.url }}">{{ post.title }}</a></span><span id="date">{{ post.date | date: "%Y-%m-%d" }}</span>
</div>
    
    {% endfor %}
    
{% endfor %}
