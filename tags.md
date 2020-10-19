---
layout: page
title: Tags
permalink: /tags/
---
{% assign tags =  site.resto | map: 'tags' | join: ','  | split: ',' | uniq %}
{% for tag in tags %}
  <h3><a name="{{tag}}">{{ tag }}</a></h3>
  <ul>
  {% for note in site.resto %}
    {% if note.tags contains tag %}
    <li><a href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}