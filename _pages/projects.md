---
layout: page
title: projects
permalink: /projects/
description: Projects where research meets design and technology.
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
_styles: |
  .projects .card {
    position: relative;
  }
  .projects .project-status {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    margin-bottom: 0.75rem;
    padding: 0.35rem 0.65rem;
    border: 1px solid rgba(65, 106, 225, 0.2);
    border-radius: 999px;
    background: #fff;
    color: rgb(65, 106, 225);
    font-size: 0.62rem;
    font-weight: 600;
    line-height: 1.2;
    letter-spacing: 0.09em;
    text-transform: uppercase;
  }
  .projects .project-status-overlay {
    position: absolute;
    top: 0.75rem;
    left: 0.75rem;
    z-index: 1;
    margin: 0;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  }
  .projects .project-status-dot {
    width: 0.35rem;
    height: 0.35rem;
    border-radius: 50%;
    background: currentColor;
  }
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" class="project-category-heading" href=".#{{ category }}">
    <h2 class="category">
      {% if category == "work" %}
        <span>Research</span>
      {% elsif category == "fun" %}
        <span>Studio</span>
      {% else %}
        <span>{{ category }}</span>
      {% endif %}
    </h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include site_project_card.liquid horizontal=true %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include site_project_card.liquid horizontal=false %}
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
      {% include site_project_card.liquid horizontal=true %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include site_project_card.liquid horizontal=false %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
