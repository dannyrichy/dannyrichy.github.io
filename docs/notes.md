---
layout: default
---

{% for note in site.notes %}
  <div>
    <strong><a href="{{ note.url }}">{{ note.title }}</a></strong> 
    <span>(Created on: {{ note.date | date: "%B %d, %Y" }})</span>
    <p>{{ note.description }}</p>
  </div>
{% endfor %}