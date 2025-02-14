---
layout: default
---
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
## Personal notes

The motivation for writing these articles are two-fold. I *suck at writing* -> *improve writing* and want to have *diary(all things ML and math)* -> *short snippets on things I find interesting/important*. I read this [article](https://perceiving-systems.blog/en/post/writing-a-good-scientific-paper) and found it as a nice guide to achieve my first goal -> try to write every article in that framework. I can't guarantee the pedantic veracity of it but I shall strive to achieve it!   

{% assign notes_by_category = site.notes | group_by: "category" %}
{% for category in notes_by_category %}
<h3>{{ category.name | escape }}</h3>
<div>
{% for note in category.items %}
<a href="{{ note.url | relative_url }}" class="download-link" style="font-size:0.8rem;color:#333"><i class="fa-regular fa-file-lines" style="color: #333;"></i> {{ note.title | escape }}</a><br>
{% endfor %}
</div>
{% endfor %}