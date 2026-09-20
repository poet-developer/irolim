---
layout: about
title: about
permalink: /
subtitle: Computational Media Researcher · Poet · Developer

profile:
  align: right
  image: prof_pic.jpg
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

I am a computational media researcher, poet, and developer exploring how people create, interpret, and communicate with artificial intelligence. My interests lie at the intersection of **human–AI collaboration, creative AI, natural language processing, and digital humanities**.

My recent work examines emotion classification and retrieval-augmented poetry generation using Korean modern poetry. Alongside my research and development work, I write poetry and published the collection *오늘도 꽃은 피어라* in 2024. I am interested in building computational systems that support human creativity while remaining attentive to the cultural and interpretive contexts of language.

<br/>
<br/>

## Education

- **2025–2026** — M.A. in Cultural Informatics, Graduate School of Korean Studies, The Academy of Korean Studies
- **2014–2019** — B.B.A. in Advertising and Public Relations, Hongik University
- **2013–2019** — B.F.A. in Digital Media Design, Hongik University

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
