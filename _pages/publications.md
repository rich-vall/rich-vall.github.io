---
layout: page
permalink: /Documentation/
title: Documentation
description: Documentation authored or co-authored by me from my projects and research.
years: [2023, 2022, 2021]
nav: true
nav_order: 5
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
