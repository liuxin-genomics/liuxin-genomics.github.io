---
title: News
layout: default
background_img: /assets/images/banner-news.jpg
welcome_msg: News
intro_msg: Keep up with our most recent advancements and discoveries in genomics.
abstract: XinLab has made steady progress in advancing genomics research across various domains. Recent efforts include contributions to plant genome evolution studies, innovations in single-cell and spatial omics technologies, and collaborative work in marine biology, clinical disease research, and agricultural genomics. These achievements reflect the lab's ongoing dedication to methodological refinement, effective data analysis, and meaningful applications, while continuing to align with its mission of contributing to the field of genomics.
---

<section class="posts-grid">
  {% for post in site.posts %}
    <article class="post-card">
      {% if post.image %}
        <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="post-image">
      {% endif %}
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="abstract"><i class="fas fa-calendar" aria-hidden="true"></i>  {{ post.date | date: "%B %d, %Y" }}</p>
      <p class="abstract">{{ post.excerpt | strip_html | truncate: 150 }}</p>
      <a href="{{ post.url | relative_url }}" class="read-more">Read More</a>
    </article>
  {% endfor %}
</section>