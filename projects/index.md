---
layout: page
title: Projects
excerpt: "Projects which Santiago E. Montesdeoca has made or been part of"
search_omit: false
---
I have had the amazing opportunity to work in these projects:

<div class="tile-list">
{% for post in site.categories.projects %}
  <article class="tile" itemscope itemtype="http://schema.org/{{post.schema}}">
    <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}" class="tile-teaser" itemprop="image">
      <img src="{{site.url}}/images/{{ post.image.tile }}" alt="{{ post.title }}">
    </a>
    <p class="entry-date">
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
    </p>
    <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}" class="tile-title" itemprop="url">
      <p itemprop="name">{{ post.title }}</p>
    </a>
    {% if post.excerpt %} <span class="tile-excerpt" itemprop="description">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}
    {% if post.read_time %}{% endif %}
  </article>
{% endfor %}
</div>
