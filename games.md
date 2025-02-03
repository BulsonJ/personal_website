---
layout: default
title: Games
---
<h1>Experience</h1>

<ul class="post-list">
  {% for post in site.posts %}
    {% if post.category == 'games' %}
    <li>

      <h2>
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
      </h2>
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      <p>
          {{ post.excerpt }}
      </p>
    </li>
    {% endif %}
  {% endfor %}
</ul>