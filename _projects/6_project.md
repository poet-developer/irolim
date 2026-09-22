---
layout: page
title: BKKSG | My Moving Web Gallery
description: "Independent Web Project · Creative Direction · UI/UX Design · Full-Stack Development"
img: assets/img/studio/bkksg_thumbnail.png
importance: 5
category: fun
research_status: completed
research_years: "2021-2023"
---

BKKSG is a personal online gallery conceived, designed, and built by **IRO LIM**. I led the entire project independently, from the initial concept and visual identity to UI/UX design, full-stack development, and deployment in 2023.

The goal was to create **a living gallery of my own**: a space where I could publish and exhibit personal creative content as it emerged. Built with Next.js, the project explores a responsive, single-page application experience with progressive web app (PWA) aspirations.

[Code](https://github.com/poet-developer/BKKSG)

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
