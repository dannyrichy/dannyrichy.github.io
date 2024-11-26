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
  <ul>
    {% for note in site.misc %}
    <li>
      <a href="{{ note.url | relative_url }}" class="note-link">{{ note.title | escape }}</a>
    </li>
    {% endfor %}
  </ul>
</section>
