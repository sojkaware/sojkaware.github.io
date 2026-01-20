---
layout: default
title: Tags
---

# Browse by Tag

<div class="tag-cloud">
  {% for tag in site.tags %}
    <a href="#{{ tag[0] | slugify }}" class="tag">{{ tag[0] }} <span class="count">({{ tag[1].size }})</span></a>
  {% endfor %}
</div>

<hr>

{% for tag in site.tags %}
  <h2 id="{{ tag[0] | slugify }}">{{ tag[0] }}</h2>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
    <!-- Also check specific collections if needed, though site.tags usually aggregates posts -->
  </ul>
{% endfor %}
