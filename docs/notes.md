---
layout: default
---

{% for note in site.notes %}
  - **[{{ note.title }}]({{ note.url }})** (Created on: {{ note.date | date: "%B %d, %Y" }})
{% endfor %}