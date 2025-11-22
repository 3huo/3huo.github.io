---
layout: home
author_profile: true
title: Home
---

# Welcome to My Blog

This is the homepage of my enhanced blog.

## Latest Posts

<div class="posts-list">
  {% for post in paginator.posts %}
    <article class="post-preview">
      <a href="{{ post.url }}">
        <h2 class="post-title">{{ post.title }}</h2>
        {% if post.subtitle %}
        <h3 class="post-subtitle">{{ post.subtitle }}</h3>
        {% endif %}
      </a>
      <p class="post-meta">
        Posted on {{ post.date | date: "%B %d, %Y" }}
      </p>
      <div class="post-entry">
        {{ post.excerpt | strip_html | truncatewords: 50 }}
        {% if post.content contains site.excerpt_separator %}
          <a href="{{ post.url }}" class="read-more">Read More</a>
        {% endif %}
      </div>
    </article>
  {% endfor %}
</div>

{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="prev">← Newer Posts</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="next">Older Posts →</a>
  {% endif %}
</div>
{% endif %}
