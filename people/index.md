---
title: Our Team
layout: default
background_img: /assets/images/banner-people.jpg
welcome_msg: People
intro_msg: Meet the talented researchers driving XinLab’s mission in genomics.
abstract: XinLab is a highly dynamic "organization"—any research team directly supervised by Xin Liu is considered part of it. As Xin Liu's responsibilities at BGI evolve, the composition of XinLab's teams is continuously adjusted. Therefore, we have listed some of the key members along with their basic information. Of course, this list is not exhaustive. If you have any suggestions or if you were once part of our team and would like to be featured here, please contact us.
---

<section class="people-grid">
  {% for person in site.people %}
    <article class="person-card">
      {% if person.photo %}
        <img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" class="person-photo">
      {% else %}
        <div class="person-photo placeholder">No Photo</div>
      {% endif %}
      <h2><a href="{{ person.url | relative_url }}">{{ person.name }}</a></h2>
      <p class="person-role">{{ person.role }}</p>
      <p class="person-summary">{{ person.summary | truncate: 100 }}</p>
      <a href="{{ person.url | relative_url }}" class="read-more">Learn More</a>
    </article>
  {% endfor %}
</section>

