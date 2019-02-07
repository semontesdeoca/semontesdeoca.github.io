---
layout: page
author: santy
title: Blog
excerpt: "An archive of blog posts from Santiago E. Montesdeoca"
search_omit: true
---
Most of my undergoing in life is documented here to keep my interested readers (mostly family and close friends) updated. This section is a continuation from my previous  [blog](http://santiagomontesdeoca.blogspot.com), for a new stage of my life.

<ul class="post-list">
{% for post in site.categories.blog %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>
    {% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}
    {% if post.read_time %} <div class="read_time"><i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</div>{% endif %}
  </a></article></li>
{% endfor %}
</ul>
