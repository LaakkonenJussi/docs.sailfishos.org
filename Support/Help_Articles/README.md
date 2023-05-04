---
title: Help Articles
permalink: Support/Help_Articles/
has_children: true
layout: default
nav_order: 150
---

<h3 class="no_toc">Contents</h3>

<ol>
{% assign sorted_pages = site.pages | sort:"nav_order" %}
{% for item in sorted_pages %}
  {% assign item_dir_parts = item.dir | remove_first: page.dir | split: '/' %}
  {% if item.dir contains page.dir and item_dir_parts.size == 1 %}
    {% unless item.nav_exclude %}
      <li>
        <a href="{{ item.url }}">{{ item.title }}</a>
      </li>
    {% endunless %}
  {% endif %}
{% endfor %}
</ol>
