---
layout: page
permalink: /publications/
title: publications
description: publications by categories in reversed chronological order.
nav: true
nav_order: 3
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications projects">

<a id="thesis" class="project-category-heading" href=".#thesis"><h2 class="category no-divider"><span>Thesis</span></h2></a>
{% bibliography --query @*[category=thesis] %}

<a id="dataset" class="project-category-heading" href=".#dataset">
  <h2 class="category no-divider"><span>Dataset</span></h2>
</a>
{% bibliography --query @*[category=dataset] %}

<a id="model" class="project-category-heading" href=".#model">
  <h2 class="category no-divider"><span>Model</span></h2>
</a>
{% bibliography --query @*[category=model] %}

<a id="prototype" class="project-category-heading" href=".#prototype">
  <h2 class="category no-divider"><span>Web Applicatinon</span></h2>
</a>
{% bibliography --query @*[category=prototype] %}

<a id="conference" class="project-category-heading" href=".#conference">
  <h2 class="category no-divider"><span>Conference Paper / Poster</span></h2>
</a>
{% bibliography --query @*[category=conference] %}

<a id="book" class="project-category-heading" href=".#book">
  <h2 class="category no-divider"><span>Book</span></h2>
</a>
{% bibliography --query @*[category=book] %}

</div>
