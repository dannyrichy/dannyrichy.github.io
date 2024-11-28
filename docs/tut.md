---
layout: niendefault
---
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
## Rndm Dump
This page serves as a collection of topics I find interesting, and as such, they may not always be accurate. I would greatly appreciate it if you could email me or raise an issue on GitHub if you find any discrepancies.
{% assign notes_by_category = site.tut | group_by: "category" %}
{% for category in notes_by_category %}
<h3>{{ category.name | escape }}</h3>
<div>
{% for note in category.items %}
<a href="{{ note.url | relative_url }}" class="download-link" style="color:#333"><i class="fa-regular fa-file-lines" style="color: #333;"></i> {{ note.title | escape }}</a><br>
{% endfor %}
</div>
{% endfor %}
