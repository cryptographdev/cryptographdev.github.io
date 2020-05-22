---
layout: page
title: Blog
---

The project posts on this site are listed below in sequence from newer to older.

<script type="text/javascript" src="https://files.coinmarketcap.com/static/widget/currency.js"></script>
<div class="coinmarketcap-currency-widget" border="0" data-currencyid="1" data-base="USD"></div>

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
