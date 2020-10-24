---
layout: page
title: Keuken
permalink: /tags/
---
<div class="container">
  <div class="row">

{% assign tags =  site.resto | map: 'tags' | join: ','  | split: ',' | uniq %}
{% for tag in tags %}
<div class='col-md-4 col-xs-12'>
  <h3><a name="{{tag}}">{{ tag }}</a></h3>
  <ul>
  {% for note in site.resto %}
    {% if note.tags contains tag %}
    <li><a href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
</div>
{% endfor %}
</div>
</div>
