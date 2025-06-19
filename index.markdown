---
layout: default
title: My Awesome Blog
---

# Welcome to My Blog!


{% comment %} Some hacky stuff to get it to show posts, at least I think this is hacky {% endcomment %}

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | strip_newlines | truncatewords: 50 }}</p>
      {% endif %}
    </li>
  {% endfor %}
</ul>

<p class="feed-subscribe">
  <a href="{{ "/feed.xml" | relative_url }}">
    <svg class="svg-icon orange">
      <use xlink:href="{{ "assets/minima-social-icons.svg#rss" | relative_url }}"></use>
    </svg><span>Subscribe via RSS</span>
  </a>
</p>