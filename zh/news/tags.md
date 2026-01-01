---
layout: default
title: "按照关键词查看"
lang: zh
permalink: /news/tags/
background_img: /assets/images/banner-news.jpg
welcome_msg: 研究进展
intro_msg: 按照关键词查看各种研究进展。
---

{% comment %} 
  1. 筛选当前语言的文章
{% endcomment %}
{% assign filtered_posts = site.posts | where: "lang", site.active_lang %}

{% comment %} 
  2. 提取所有标签并去重
{% endcomment %}
{% assign raw_tags = "" %}
{% for post in filtered_posts %}
  {% for tag in post.tags %}
    {% assign raw_tags = raw_tags | append: tag | append: "," %}
  {% endfor %}
{% endfor %}
{% assign tag_list = raw_tags | split: "," | uniq | sort %}


<div class="tags-cloud-container mb-5 p-4 bg-white border rounded">
  <div class="d-flex flex-wrap gap-3">
    {% for tag_name in tag_list %}
      {% if tag_name == "" %}{% continue %}{% endif %}
      
      {% comment %} 统计当前语言下该标签的文章数 {% endcomment %}
      {% assign count = 0 %}
      {% for post in filtered_posts %}
        {% if post.tags contains tag_name %}
          {% assign count = count | plus: 1 %}
        {% endif %}
      {% endfor %}

      <a href="{{ '/news/tags/' | append: tag_name }}/" class="btn btn-outline-primary d-inline-flex align-items-center">
        <i class="fas fa-tag me-2"></i>
        {{ site.data.translations[tag_name] | default: tag_name }}
        <span class="badge bg-primary ms-2">{{ count }}</span>
      </a>
    {% endfor %}
  </div>
</div>

<style>
  .tags-cloud-container {
    box-shadow: 0 .125rem .25rem rgba(0,0,0,.075);
  }
  .btn-outline-primary {
    border-radius: 50px; /* 胶囊状按钮 */
    padding: 8px 20px;
    transition: all 0.3s;
  }
  .btn-outline-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  }
</style>