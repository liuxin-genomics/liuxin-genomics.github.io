---
layout: default
title: 发表论文
lang: zh
permalink: /publications/
load_echarts: true
background_img: /assets/images/banner-publications.jpg
# 以下是页面内显示的文字翻译
welcome_msg: 发表论文
intro_msg: 参与发表超过200篇高质量科学论文，在基因组学研究领域表现卓越。
abstract: >
  XinLab 参与发表了200多篇学术论文，其中40篇论文为主要参与者。
  您可以访问我们的 <a href="https://scholar.google.com/citations?user=UkTazWQAAAAJ&hl=en" target="_blank">Google 学术主页</a>了解更多详细信息。
chart_year_title: 年度发表趋势
table_title: 论文列表详细信息
---

<div class="container mt-5">

    <div id="statusMessage" class="status-message alert alert-info" style="display: none;"></div>

    <div class="row">
        <h3>{{ page.chart_year_title }}</h3>
        <div id="publicationsByYearChart" class="chart-container"></div>
    </div>

    <div class="page-content mt-5">
        <h3>{{ page.table_title }}</h3>
        <div class="table-container">
            <table id="publicationsTable" class="table table-striped table-bordered" style="width:100%">
                </table>
        </div>
    </div>
</div>

{% include publication-scripts.html %}