---
layout: page
title: BKKSG | My Moving Web Gallery
description: "Independent Web Project · Creative Direction · UI/UX Design · Full-Stack Development"
img: assets/img/studio/bkksg_thumbnail.png
importance: 5
category: fun
research_status: completed
research_years: "2021-2023"
_styles: |
  .co-reading-interface-link {
    display: inline-block;
    padding: 0.65rem 1rem;
    border: 2px solid var(--global-theme-color);
    border-radius: 0.5rem;
    color: var(--global-theme-color);
    font-weight: 700;
    text-decoration: none;
  }
  .co-reading-interface-link:hover,
  .co-reading-interface-link:focus-visible {
    background: var(--global-theme-color);
    color: #fff;
    text-decoration: none;
  }
  .co-reading-figure {
    margin-left: auto;
    margin-right: auto;
    text-align: center;
  }
  .co-reading-figure img {
    margin-left: auto;
    margin-right: auto;
  }
  .co-reading-figure figcaption {
    text-align: center;
  }
  .co-reading-tag {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    margin: 0 0 1rem;
    padding: 0.35rem 0.8rem;
    border: 1px solid rgba(65, 106, 225, 0.25);
    border-radius: 999px;
    color: var(--global-theme-color);
    font-size: 0.8rem;
    letter-spacing: 0.04em;
  }
---

<div class="co-reading-tag" title="Standing aside - 비껴서기, written as it sounds in Korean">
  <span>bikkyeoseogi</span><span aria-hidden="true">·</span><span lang="ko">비껴서기</span>
</div>

BKKSG is a personal online gallery conceived, designed, and built by **IRO LIM**. I led the entire project independently, from the initial concept and visual identity to UI/UX design, full-stack development, and deployment in 2023.

The goal was to create **a living gallery of my own**: a space where I could publish and exhibit personal creative content as it emerged. Built with Next.js, the project explores a responsive, single-page application experience with progressive web app (PWA) aspirations.

<p style="display: flex; flex-wrap: wrap; gap: 0.75rem;">
  <a class="co-reading-interface-link" href="https://poet-developer.github.io/KPoEMInterface/">Explore BKKSG →</a>
</p>

[📁Code](https://github.com/poet-developer/BKKSG)

## Concept & Visual Design

The visual concept brings together **comets** and **jogakbo**, traditional Korean patchwork textiles. These references shape the gallery's sense of movement and composition, with an HTML5 Canvas animation exploring the forms of jogakbo. A time-based color theme allows the site's appearance to change throughout the day.

## Gallery Experience

- **Responsive masonry layout:** A Pinterest-style grid adapts to different screen sizes through media queries, creating a flexible setting for visual content.
- **Infinite scrolling:** Visitors can continue browsing without navigating through separate pagination controls.
- **Search modal:** Content can be searched by title and body text.
- **Time-based themes:** Styled-components and session storage support changes to the site's color theme based on the time of day.
- **Scroll restoration:** Session storage preserves the previous scroll position when visitors return to the gallery.
- **NFT purchase links:** Links connect visitors to NFT purchase pages.

## Full-Stack Development

I developed an administrator-only CRUD system to create, read, update, and delete gallery content. The publishing workflow integrates the TinyMCE React rich-text editor for creating and editing posts, alongside AWS S3 and Lambda for storage and backend functionality.

The application uses **Next.js, React, and Node.js**, with **MySQL** for data storage and **HTML5 Canvas** for animation. I also handled deployment on **AWS Lightsail**, using **Docker and Portainer** to manage containers and **NGINX** for web serving, reverse proxying, and HTTPS configuration.

## Project Planning

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/studio/bkksg_planning.jpg" title="BKKSG project planning" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Planning for BKKSG, independently conceived, designed, and developed by Iro Lim.
</div>
