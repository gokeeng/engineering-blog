---
layout: default
title: All Posts
permalink: /posts/
---

# All Posts

<div class="post-list">
{% for post in site.posts %}
  <article class="post-entry">
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <time class="post-date" datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
    {% if post.excerpt %}
      <div class="post-excerpt">
        {{ post.excerpt | strip_html | truncatewords: 50 }}
      </div>
    {% endif %}
    {% if post.tags.size > 0 %}
      <div class="post-tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
    {% endif %}
  </article>
{% endfor %}
</div>

{% if site.posts.size == 0 %}
  <p>No posts yet. Start writing your first blog post!</p>
{% endif %}
