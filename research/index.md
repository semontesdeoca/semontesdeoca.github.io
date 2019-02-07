---
layout: page
title: Research
excerpt: "An archive of research/technical articles sorted by date."
search_omit: true
---
My current research is on watercolor rendered animation, for which I am developing real-time technology that makes it all possible. I will be sharing research articles, some insight and informative articles for the technically/research inclined professionals and students.

<ul class="post-list">
{% for post in site.categories.articles %}
  <li><article>
  <a href="{{ site.url }}{{ post.url }}">
  <span class="citation {{ post.type | downcase | replace: ' ', '-' | replace: '.', ''}}">{{ post.type }}</span>
  {{ post.title }}
  <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>

  {% if post.citation %}
  <div class="excerpt">{{post.citation}}
  <span class="authors">{{post.authors}}</span><span>: {{post.title}}. </span><span class="publication">{{post.publication}}</span><span> ({{post.year}}), {{post.publisher}}{% if post.pages %}, pp. {{post.pages}}{% endif %}.</span>
  </div>
  {% else %}
    {% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}
    {% if post.read_time %} <div class="read_time"><i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</div>{% endif %}
  {% endif %}
  </a></article></li>
{% endfor %}
</ul>
