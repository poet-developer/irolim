---
layout: about
title: about
permalink: /
subtitle: Computational Media Researcher · Poet · Developer

profile:
  align: right
  image: prof_pic.png
  image_circular: false # crops the image to make it circular

selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 10 # number of news items shown per page

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<div class="about-content" markdown="1">

I am a computational media researcher, poet, and developer interested in designing environments in which people interpret and make meaning with artificial intelligence. My research brings together **human–computer interaction (HCI), media aesthetics, artificial intelligence, art, and digital humanities**. I explore how datasets, models, and interfaces shape the ways we encounter cultural works and participate in interpretation.

My master’s thesis, <a href="{% link _projects/7_project.md %}" style="color: var(--global-theme-color);"><em style="color: inherit;">Co-Reading with AI: Color Visualization of Emotion Data in Korean Modern Poetry</em></a>, was supervised by Professor Byungjun Kim at The Academy of Korean Studies. The research translated emotions in modern Korean poetry into color, realizing the full research process from dataset construction and model development to an interface prototype. Over the course of my two-year master’s program, I led the project toward a single research goal, progressively developing and presenting its components at seven national and international conferences. As part of this process, I also conducted collaborative research that resulted in a first-author journal publication and laid the groundwork for my thesis. The thesis project was selected for the **2025 Master’s Student Research Grant**, awarded to 100 researchers nationwide, and was funded by the Ministry of Education of the Republic of Korea and the National Research Foundation of Korea (NRF-2025S1A5B5A20019820).The project brought together my long-standing interests in media, design, and AI, which I had been exploring since my undergraduate years, into a shared environment for literary interpretation.

I am currently working with Professor Baro Kim as a full-stack developer on an [AI Cultural Heritage Docent Web Prototype]({% link _projects/11_project.md %}). The project combines cultural heritage knowledge with generative AI to develop explanations responsive to visitors’ backgrounds and languages, extending my interest in environments for human–AI interpretation to cultural heritage.

<br/>
<br/>

## Education

- **2024–2026** — Master of Arts (M.A.) in Cultural Informatics, Graduate School of Korean Studies, The Academy of Korean Studies
- **2014–2019** — Bachelor of Business Administration (B.B.A.) in Advertising and Public Relations, Hongik University
- **2013–2019** — Bachelor of Fine Arts (B.F.A.) in Digital Media Design, Hongik University

<br/>

## Work Experience

- **2025–2026** — Web Designer and Web Publisher, Korean Modern Literature Scholars Conference
- **2025–2026** — CI and Web Designer, DH2026, Alliance of Digital Humanities Organizations (ADHO)
- **2024–2026** — Researcher, Center for Digital Humanities at The Academy of Korean Studies
- **2023–Present** — Columnist, Cosmian News
- **Mar–Apr 2025** — Exhibition Planning and Design, Art Seoul 2025, Hangaram Art Museum
- **Jan 2025** — Exhibition Planning and Design, WORLD ART EXPO 2025, COEX
- **Sep 2024** — Web and CI Design, AKS Center for Digital Humanities
- **Jun 2023** — Exhibition Brand Design, *CROSSING ONE*, H.ART1
- **2013–2019** — Band Vocalist

</div>

<script>
  (() => {
    const title = document.querySelector(".post:has(.about-content) .post-title");
    if (!title || title.querySelector(".about-logo-link")) return;

    const logoLink = document.createElement("a");
    logoLink.className = "about-logo-link";
    logoLink.href = "https://bkksg.com";
    logoLink.target = "_blank";
    logoLink.rel = "noopener noreferrer";
    logoLink.setAttribute("aria-label", "Visit BKKSG.com");
    title.append(logoLink);
  })();
</script>

<br/>
