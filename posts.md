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

<style>
.post-list {
  margin-top: 2rem;
}

.post-entry {
  margin-bottom: 2rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #eee;
}

.post-entry:last-child {
  border-bottom: none;
}

.post-entry h2 {
  margin: 0 0 0.5rem 0;
  font-size: 1.5rem;
}

.post-entry h2 a {
  text-decoration: none;
  color: #333;
}

.post-entry h2 a:hover {
  color: #0066cc;
}

.post-date {
  color: #666;
  font-size: 0.9rem;
  display: block;
  margin-bottom: 0.5rem;
}

.post-excerpt {
  color: #555;
  line-height: 1.5;
  margin-bottom: 0.5rem;
}

.post-tags {
  margin-top: 0.5rem;
}

.tag {
  display: inline-block;
  background: #f0f0f0;
  color: #666;
  padding: 0.2rem 0.5rem;
  margin-right: 0.5rem;
  border-radius: 3px;
  font-size: 0.8rem;
}
</style>
