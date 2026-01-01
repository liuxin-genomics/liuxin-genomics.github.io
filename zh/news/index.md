---
title: 进展
layout: default
lang: zh
permalink: /news/
background_img: /assets/images/banner-news.jpg
welcome_msg: 查看进展
intro_msg: 关注我们的最新研究成果，以及其他基因组学领域的精彩发现。
abstract: 
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