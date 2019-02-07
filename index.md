---
layout: page
excerpt: "Welcome to Artineering"
search_omit: true
---
{::options parse_block_html="true" /}
<div class='front-page'>
## Welcome to Artineering!
The website of **Santiago Montesdeoca**, an artist/engineer contributing to the world, one pixel at a time.

Feel free to explore the [blog](/blog/), read academic/technical animation related [articles](/research/) or view the [projects](/projects/) I am or have been part of.

If you like what you find or just want to say hi, make sure you [drop me a line](/about#contact)!

### Latest posts

<ul class="post-list" style="margin-top: -20px">
{% for post in site.posts limit:10 %}
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
</div>

<!--data-tweet-limit="3"-->
<div class="responsive-twitter">
<a class="twitter-timeline" height="1020" href="https://twitter.com/{{site.owner.twitter}}" data-widget-id="722401536261763072">Latest from @{{ site.owner.twitter }}</a>
<script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>
</div>
