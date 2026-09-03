---
layout: default
---
<h2>Posts</h2>
<ul class="posts">
{% for post in site.posts %}
  <li>
    <span class="date">{{ post.date | date: "%b %d, %Y" }}</span>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
