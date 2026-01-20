---
layout: default
title: Games
tags: [games, web, mobile, fun]
---

# Games

Some fun projects I've worked on.

## Mobile Games

- **[Jankudlacek Fashion Saloon](https://play.google.com/store/apps/details?id=com.sojkaware.jankudlacekfashionsaloon&hl=cs)**
  <br><em>A mobile fashion experience.</em>

## Web Games

- **[Tunneler](https://sojkaware.github.io/Tunneler/index.html)**
  <br><em>HTML5 remake of the classic tank game.</em>

## All Game Projects

<ul>
{% assign games = site.games %}
{% for game in games %}
  <li><a href="{{ game.url | relative_url }}">{{ game.title }}</a></li>
{% endfor %}
</ul>
