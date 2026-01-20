---
layout: default
title: Apps
---

# Apps

Here you can find all privacy-first utility applications for Android.

{% assign apps = site.apps %}
{% if apps.size > 0 %}
  <ul>
  {% for app in apps %}
    <li><a href="{{ app.url | relative_url }}">{{ app.title }}</a></li>
  {% endfor %}
  </ul>
{% else %}
  <p><em>No apps listed yet. Check back soon!</em></p>
{% endif %}

<!-- If you want to list posts with 'app' category instead, use this: -->
<!-- 
<ul>
  {% for post in site.categories.apps %}
    <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
-->
