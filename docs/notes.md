---
layout: default
---

## Academics

{% assign notes_by_category = site.notes | group_by: "category" %}
{% for category in notes_by_category %}
  <h3>{{ category.name }}</h3>
  {% for note in category.items %}
    {% raw %}
    <div>
      <strong><a href="{{ note.url }}">{{ note.title }}</a></strong>
      <span style="color: grey;">({{ note.date | date: "%B %d, %Y" }})</span>
      <p>{{ note.description }}</p>
    </div>
    {% endraw %}
  {% endfor %}
{% endfor %}