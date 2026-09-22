---
layout: page
title: AI Cultural Heritage Docent Web Prototype
description: "Graph-RAG · Cultural Heritage · Semantic Knowledge Graphs · Adaptive Interpretation"
importance: 4
category: work
research_status: in_progress
related_publications: true
---

<p><strong>This research develops an AI cultural heritage docent web prototype that combines a semantic knowledge graph with generative AI to support responsible, visitor-adaptive interpretation.</strong> It explores how explanations can respond to a visitor's knowledge and language while remaining grounded in documented cultural heritage information and institutional guidelines.</p>

<p><strong>Research team:</strong> Song-yi Jung · Iro Lim · Baro Kim<br>
The Academy of Korean Studies</p>

<h2>Research Context</h2>

<p>Physical heritage signage offers limited space and generally presents the same explanation to every visitor. General-purpose language models can offer more flexible responses, but may introduce unsupported historical claims. This project addresses both challenges by connecting generation to structured domain knowledge and explicit principles for heritage interpretation.</p>

<p>The case study is the <strong>Hanging Painting of Janggoksa Temple (Maitreya Buddha, 1673)</strong>. Its rich iconography and <em>hwagi</em> (畫記, painting inscription) connect figures, monk-painters, donations, materials, and production activities, making it a useful case for modeling both terminology and historical relationships.</p>

<h2>Knowledge Modeling & Narrative Guidelines</h2>

<p>The research organizes four kinds of source material—basic artwork information, inscription records, person records, and a thesaurus—into <strong>RDF/OWL semantic data</strong>. SKOS structures the iconographic vocabulary, while CIDOC CRM provides modeling terms for relationships among people, works, places, and events.</p>

<p>This semantic representation is converted into a <strong>Neo4j property graph</strong> for retrieval. RDF/OWL supports knowledge modeling and scholarly sharing, while Neo4j supports the application's queries. Multilingual names and alternative terms retain source-identifying prefixes so that their origins can be traced.</p>

<p>Alongside the factual data, Korea Heritage Service signage guidelines are expressed as constraints in the system prompt. This layer guides narrative structure and terminology, with the aim of reducing unsupported statements and maintaining appropriate interpretive language.</p>

<h2>System Architecture</h2>

<figure>
  <img src="{{ '/assets/img/studio/ai_docent_System_architecture.jpg' | relative_url }}" alt="AI docent architecture connecting cultural heritage knowledge and guideline data to a Graph-RAG engine, audience and language selection, and text-based and image-based interfaces." loading="lazy" style="display: block; width: 100%; height: auto;">
  <figcaption>System architecture: knowledge and guideline data, Graph-RAG retrieval and generation, and two visitor interaction modes.</figcaption>
</figure>

<p>The backend routes questions to predefined <strong>Cypher queries</strong> that retrieve relevant graph records. <strong>LangChain</strong> combines those results with institutional guidelines and the visitor's selected context in a prompt for <strong>Google Gemini</strong>. The generated explanation is intended to reflect both the retrieved evidence and the visitor's level of familiarity.</p>

<p>The web prototype uses a <strong>Next.js frontend</strong> and a <strong>FastAPI backend</strong>. Its adaptive interface supports audience and language selection, allowing the same source material to inform explanations for children, general visitors, and specialists.</p>

<h2>Two Modes of Interaction</h2>

<h3>Mode 1: Text-driven Description Generation</h3>

<p>The prototype provides a button-based interface for selecting question types and receiving explanations grounded in retrieved data. Audience and language preferences guide the explanation's wording and difficulty.</p>

<h3>Mode 2: Image-driven Interactive Description</h3>

<p>The proposed image-based mode uses <strong>SVG hotspots</strong> on significant iconographic elements. Selecting a detail is designed to trigger retrieval of its associated graph data and generate a contextual explanation. This connects visual exploration with structured knowledge and source references.</p>

<h2>Research Status & Next Steps</h2>

<p>The project remains in development. User studies and quantitative evaluation are needed to assess interpretive accuracy, usability, and the effectiveness of its grounding and guideline mechanisms. Future work considers extending the approach to other heritage objects and interactive exhibition settings, including AR and 3D environments.</p>

<h2>Project Presentation</h2>

<iframe
  src="{{ '/assets/img/research/AI%20Cultural%20Heritage%20Docent%20Web%20Prototype.pdf' | relative_url }}"
  title="AI Cultural Heritage Docent Web Prototype presentation"
  width="100%"
  height="800"
  style="display: block; height: 80vh; border: 0;"
></iframe>

<p><a href="{{ '/assets/img/research/AI%20Cultural%20Heritage%20Docent%20Web%20Prototype.pdf' | relative_url }}" target="_blank" rel="noopener">Open project presentation (PDF)</a></p>

<h2>Live Demo</h2>

<video controls playsinline preload="metadata" aria-label="AI Cultural Heritage Docent Web Prototype live demo" style="display: block; max-width: 500px; height: auto;">
  <source src="{{ '/assets/Live_Demo%20%283%29.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support embedded video. Please use the link below to watch the demo.
</video>

<p><a href="{{ '/assets/Live_Demo%20%283%29.mp4' | relative_url }}" target="_blank" rel="noopener">Open live demo video</a></p>