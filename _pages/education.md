---
layout: page
permalink: /education/
title: Education
description: 
nav: true
nav_order: 3
display_categories: [academics]
horizontal: false
---

### Master 2 MVA (Math, Vision, Learning)
- **Institution:** École Normale Supérieure Paris-Saclay & Université Paris-Saclay  
- **Date:** 2023 - 2024  
- **Achievement:** 17.6/20  

### International Semester
- **Institution:** University of Southampton  
- **Date:** January to June 2023  
- **Achievement:** GPA 4.0  
- **English Proficiency:** TOEIC 930/990, Duolingo C1  

### Aerospace Engineering
- **Institution:** ESTACA: School of Aeronautical and Automotive Engineering  
- **Date:** 2019 - 2022
- **Achievement:** Valedictorian (1/89) - Vice-president of SIERA

---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}

  <!-- 
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  -->
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
