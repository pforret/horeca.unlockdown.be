---
layout: page
title: Category
permalink: /category/
---
{% assign cats =  site.resto | map: 'category' | join: ','  | split: ',' | uniq %}
{% for cat in cats %}
  <h3><a name="{{cat}}">{{ cat }}</a></h3>
  <ul>
  {% for note in site.resto %}
    {% if note.category contains cat %}
    <li><a href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}