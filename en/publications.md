---
layout: default
title: Publications
lang: en
permalink: /publications/
load_echarts: true
background_img: /assets/images/banner-publications.jpg
# Translations for English version
welcome_msg: Publications
intro_msg: Contributing to Over 180 Scientific Publications with Excellence in Genomics Research.
abstract: >
  A total of more than 180 scientific papers have been published with XinLab's participation, 
  among which more than 39 papers were published as major participants. 
  You can visit our <a href="https://scholar.google.com/citations?user=UkTazWQAAAAJ&hl=en" target="_blank">Google Scholar profile</a> for more details.
chart_year_title: Publications by Year
table_title: Publications List
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