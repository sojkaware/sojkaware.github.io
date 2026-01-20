---
layout: default
title: Tags
---

# Browse by Tag

{% capture site_tags %}{% for tag in site.tags %}{{ tag[0] }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign tag_words = site_tags | split:',' | sort %}

<!-- 
  Jekyll's site.tags usually only captures POSTS. 
  To support PAGES, we must iterate through site.pages and build the list manually. 
-->

{% assign all_tags = "" | split: "," %}
{% for page in site.pages %}
  {% if page.tags %}
    {% for tag in page.tags %}
      {% assign all_tags = all_tags | push: tag %}
    {% endfor %}
  {% endif %}
{% endfor %}
{% assign all_tags = all_tags | uniq | sort %}

<div class="tag-cloud">
  {% for tag in all_tags %}
    <a href="#{{ tag | slugify }}" class="tag">{{ tag }}</a>
  {% endfor %}
</div>

<hr>

{% for tag in all_tags %}
  <h2 id="{{ tag | slugify }}">{{ tag }}</h2>
  <ul>
    {% for page in site.pages %}
      {% if page.tags contains tag %}
        <li><a href="{{ page.url | relative_url }}">{{ page.title }}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}
