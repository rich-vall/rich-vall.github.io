---
layout: page
title: Triton Robotics
permalink: /tritonrobotics/
description: A growing collection of your cool projects.
nav: true
nav_order: 3
display_categories: [Year 2, Year 1]
horizontal: false
---

<!-- pages/tritonrobotics.md -->
<div class="tritonrobotics">
{%- if site.enable_tritonrobotics_categories and page.display_categories %}
  <!-- Display categorized tritonrobotics -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_tritonrobotics = site.tritonrobotics | where: "category", category -%}
  {%- assign sorted_tritonrobotics = categorized_tritonrobotics | sort: "importance" %}
  <!-- Generate cards for each tritonrobotics -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_tritonrobotics -%}
      {% include tritonrobotics_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for tritonrobotics in sorted_tritonrobotics -%}
      {% include tritonrobotics.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display tritonrobotics without categories -->
  {%- assign sorted_tritonrobotics = site.tritonrobotics | sort: "importance" -%}
  <!-- Generate cards for each tritonrobotics -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for tritonrobotics in sorted_tritonrobotics -%}
      {% include tritonrobotics_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for tritonrobotics in sorted_tritonrobotics -%}
      {% include tritonrobotics.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
