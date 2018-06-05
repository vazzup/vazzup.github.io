---
title: Blog
layout: default
---
# All Posts
<ul>
	{% for post in site.posts %}
		<li>
			<a href="{{ post.url }}" style="font-size: 1.5em">{{ post.title }}</a>
			<br>
			<time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
		</li>
	{% endfor %}

</ul>
