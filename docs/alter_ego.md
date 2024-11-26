---
layout: niendefault
---
<div class="img-container">
  <img src="/assets/profile_blur.jpg" alt="profile image" />
</div>
# DANNY BOY
<p style="text-align: justify;">
This is the alternate side meant to track all other things
</p>

<section>
  {% assign notes_by_category = site.misc | group_by: "category" %}
  {% for category in notes_by_category %}
  <h3>{{ category.name | escape }}</h3>
  <ul>
    {% for note in category.items %}
    <li>
      <a href="{{ note.url | relative_url }}" class="note-link">{{ misc.title | escape }}</a>
    </li>
    {% endfor %}
  </ul>
  {% endfor %}
</section>


