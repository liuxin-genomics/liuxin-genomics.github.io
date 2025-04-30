---
title: News
layout: default
background_img: /assets/images/banner-news.jpg
welcome_msg: News
intro_msg: Stay updated on our recent findings and other's intriguing discoveries in genomics.
abstract: XinLab has steadily advanced genomics research across diverse fields—from plant genome evolution to innovations in single‐cell and spatial omics, as well as collaborative projects in marine biology, clinical disease research, and agricultural genomics. These accomplishments underscore our commitment to refining methods, enhancing data analysis, and delivering meaningful applications—all in line with our mission to contribute to the genomics field. We also share our insights on some of the most intriguing recent studies, which we categorize as "frontiers."

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