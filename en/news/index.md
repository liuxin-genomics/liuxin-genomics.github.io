---
title: News
layout: default
lang: en
permalink: /news/
background_img: /assets/images/banner-news.jpg
welcome_msg: News
intro_msg: Stay updated on our recent findings and other's intriguing discoveries in genomics.
abstract: XinLab has steadily advanced genomics research across diverse fields—from plant genome evolution to innovations in single‐cell and spatial omics, as well as collaborative projects in marine biology, clinical disease research, and agricultural genomics. These accomplishments underscore our commitment to refining methods, enhancing data analysis, and delivering meaningful applications—all in line with our mission to contribute to the genomics field. We also share our insights on some of the most intriguing recent studies, which we categorize as "frontiers."

---
{% assign filtered_posts = site.posts | where: "lang", site.active_lang %}

<section class="posts-grid">
  {% for post in filtered_posts %}
    <article class="post-card">
      {% if post.image %}
        <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="post-image">
      {% endif %}
      
      <h2><a href="{{ post.url | relative_url }}" style="text-decoration: none;">{{ post.title }}</a></h2>
      
      <p class="abstract">
        <i class="fas fa-calendar" aria-hidden="true"></i>  
        {% comment %} 日期格式化：中文用年-月-日，英文用月-日-年 {% endcomment %}
        {% if site.active_lang == 'zh' %}
          {{ post.date | date: "%Y年%m月%d日" }}
        {% else %}
          {{ post.date | date: "%B %d, %Y" }}
        {% endif %}
      </p>

      <p class="abstract">{{ post.excerpt | strip_html | truncate: 150 }}</p>
      
      <a href="{{ post.url | relative_url }}" class="read-more">
        {% if site.active_lang == 'zh' %}阅读全文{% else %}Read More{% endif %}
      </a>
    </article>
  {% endfor %}
</section>