---
layout: page
title: Blog
---

<p>The project posts on this site are listed below in sequence from newer to older.</p>

<p><script type="text/javascript" src="https://files.coinmarketcap.com/static/widget/currency.js"></script>
<div data-currencyid="1" data-base="USD" style="border:none; padding:20px"></div></p>

{% assign postsByYear = (site.categories.['blog'] | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h2>{{ year.name }}</h2>
<ul>
{% for post in year.items %}
{% assign postYear = post.date | date:"%Y" %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>		
{% endfor %}
</ul>	
{% endfor %}
