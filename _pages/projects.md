---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 3
display_categories: [siera, projects]
horizontal: false
---


### Competitions

<div class="projects">
  {% comment %}
    1. Get all Siera projects.
    2. Sort them by "importance".
  {% endcomment %}
  {% assign siera_projects = site.projects | where: "category", "siera" | sort: "importance" %}

  {% if page.horizontal %}
    <div class="container">
      <div class="row row-cols-1 row-cols-md-2">
      {% for project in siera_projects %}
        {% include projects_horizontal.liquid %}
      {% endfor %}
      </div>
    </div>
  {% else %}
    <div class="row row-cols-1 row-cols-md-3">
      {% for project in siera_projects %}
        {% include projects.liquid %}
      {% endfor %}
    </div>
  {% endif %}
</div>


### Personal Projects

<div class="projects">
  {% comment %}
    1. Get all Personal projects (assuming "projects" is your personal category).
    2. Sort them by "importance".
  {% endcomment %}
  {% assign personal_projects = site.projects | where: "category", "projects" | sort: "importance" %}

  {% if page.horizontal %}
    <div class="container">
      <div class="row row-cols-1 row-cols-md-2">
      {% for project in personal_projects %}
        {% include projects_horizontal.liquid %}
      {% endfor %}
      </div>
    </div>
  {% else %}
    <div class="row row-cols-1 row-cols-md-3">
      {% for project in personal_projects %}
        {% include projects.liquid %}
      {% endfor %}
    </div>
  {% endif %}
</div>