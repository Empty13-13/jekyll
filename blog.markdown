---
layout: page
title: Blog
---

{% assign liString = "//" %}
{% assign byYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}

<p>{{site.posts.lenght}}</p>

{% for yearItem in byYear %}
<h1 class="blog__year">{{ yearItem.name }}</h1>
  <ul>
    {% for post in yearItem.items %}
    <li>{{liString}} {{post.date | date: '%d %b'}} >> <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

`blob`