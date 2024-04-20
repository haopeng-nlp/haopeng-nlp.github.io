---
layout: page
title: group
permalink: /group/
nav: true
horizontal: false
nav_order: 2
display_categories: ["PhD students", "Masters students", "student collaborators"]
---



<!-- pages/projects.md -->
<div class="projects">
<h2 class="category"> <b>prospective students</b></h2>
I will be taking a couple of graduate students this coming cycle. Checkout <a href="https://haopeng-nlp.github.io/publications/" style="text-decoration:none">my research</a>. Please apply to <a href="https://grad.illinois.edu/admissions/apply" style="text-decoration:none">UIUC CS Ph.D. program</a> if you are interested in working with me.

{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category"> <b> {{ category }}</b></h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
    <br><br>
  {% endfor %}


{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>