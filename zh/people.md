---
title: 团队成员
layout: default
lang: zh
permalink: /people/
background_img: /assets/images/banner-people.jpg
welcome_msg: 团队成员
intro_msg: 认识一下我们的团队成员。
abstract: XinLab，不断发展，我们列出了一些核心成员及其基本信息，当然，这份名单并不完整。如果您有任何建议，或者您曾经是我们团队的一员并希望在此展示，请与我们联系。
---
{% assign filtered_people = site.people | where: "lang", site.active_lang %}

<section class="people-grid">
  {% for person in filtered_people %}
    <article class="person-card">
      {% if person.photo %}
        <img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" class="person-photo">
      {% else %}
        <div class="person-photo placeholder">没有照片</div>
      {% endif %}
      <h2><a href="{{ person.url | relative_url }}">{{ person.name }}</a></h2>
      <p class="person-role">{{ person.role }}</p>
      <p class="person-summary">{{ person.summary | truncate: 100 }}</p>
      <a href="{{ person.url | relative_url }}" class="read-more">了解详情</a>
    </article>
  {% endfor %}
</section>

