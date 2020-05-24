---
layout: page
title: Categories
---

<p>The posts on this site are in categories and listed below in sequence from newer to older.</p>

{% assign postsByYear = (site.categories.['books'] | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h2>Books ({{ year.name }})</h2>
<ul>
{% for post in year.items %}
{% assign postYear = post.date | date:"%Y" %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>		
{% endfor %}
</ul>	
{% endfor %}
