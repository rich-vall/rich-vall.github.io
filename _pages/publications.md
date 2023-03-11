---
layout: page
permalink: /Documentation/
title: Documentation
description: Documentation authored or co-authored by me from my projects and research.
years: [2021, 2022, 2023]
nav: true
nav_order: 6
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
