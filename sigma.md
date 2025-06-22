---
layout: default
title: SIGMA Brief
permalink: /sigma/
---

<div class="tag-page">
  <header class="tag-header">
    <h1 class="tag-title">SIGMA Briefs</h1>
    <p class="tag-description">All posts tagged with SIGMA</p>
    <div class="post-count">{{ site.tags.SIGMA.size }} posts found</div>
  </header>

  <div class="posts-grid">
    {% for post in site.tags.SIGMA %}
      <article class="post-card">
        <div class="post-card-header">
          <h2 class="post-card-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h2>
          <div class="post-card-meta">
            <time datetime="{{ post.date | date_to_xmlschema }}">
              {{ post.date | date: "%B %d, %Y" }}
            </time>
            {% if post.author %}
              <span class="post-author">by {{ post.author }}</span>
            {% endif %}
          </div>
        </div>
        
        <div class="post-card-content">
          {% if post.excerpt %}
            <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
          {% endif %}
        </div>
        
        <div class="post-card-footer">
          {% if post.tags.size > 0 %}
            <div class="post-tags">
              {% for tag in post.tags %}
                <span class="tag">{{ tag }}</span>
              {% endfor %}
            </div>
          {% endif %}
          <a href="{{ post.url | relative_url }}" class="read-more-btn">Read More →</a>
        </div>
      </article>
    {% endfor %}
  </div>

  {% if site.tags.SIGMA.size == 0 %}
    <div class="no-posts">
      <h3>No posts found</h3>
      <p>There are no posts tagged with SIGMA yet.</p>
    </div>
  {% endif %}
</div>