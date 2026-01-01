---
layout: default
title: "News by Categories"
lang: en
permalink: /news/categories/
background_img: /assets/images/banner-news.jpg
welcome_msg: News
intro_msg: Stay updated on our recent findings and other's intriguing discoveries in genomics.
---
{% comment %} 
  1. 筛选当前语言的文章
{% endcomment %}
{% assign filtered_posts = site.posts | where: "lang", site.active_lang %}

{% comment %} 
  2. 提取并去重所有分类名
{% endcomment %}
{% assign raw_categories = "" %}
{% for post in filtered_posts %}
  {% for cat in post.categories %}
    {% assign raw_categories = raw_categories | append: cat | append: "," %}
  {% endfor %}
{% endfor %}
{% assign category_list = raw_categories | split: "," | uniq | sort %}


<div class="category-list-container mb-5">
  <ul class="list-group">
    {% for category_name in category_list %}
      {% if category_name == "" %}{% continue %}{% endif %}
      
      {% comment %} 统计当前分类在当前语言下的文章数 {% endcomment %}
      {% assign count = 0 %}
      {% for post in filtered_posts %}
        {% if post.categories contains category_name %}
          {% assign count = count | plus: 1 %}
        {% endif %}
      {% endfor %}

      <li class="list-group-item d-flex justify-content-between align-items-center">
        <a href="{{ '/news/categories/' | append: category_name}}/" class="h5 mb-0 text-decoration-none">
          <i class="fas fa-folder-open me-2"></i>
          {{ category_name|capitalize }}
        </a>
        <span class="badge bg-primary rounded-pill">{{ count }}</span>
      </li>
    {% endfor %}
  </ul>
</div>

<style>
  .list-group-item:hover { background-color: #f8f9fa; }
  .list-group-item a { color: #333; transition: color 0.2s; }
  .list-group-item a:hover { color: #ee5a24; }
</style>