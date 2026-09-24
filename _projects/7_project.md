---
layout: page
title: Co-Reading with AI
description: "Master’s Thesis · Color Visualization of Emotion Data in Korean Modern Poetry"
img:
importance: 1
category: work
research_status: completed
research_years: "2024-2026"
related_publications: false
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
  .co-reading-case {
    margin: 3.5rem 0 1.5rem;
    padding: 1.75rem clamp(1rem, 4vw, 2rem);
    border: 1px solid var(--global-divider-color);
    border-top: 6px solid #8bc4a6;
    border-radius: 0 0 0.75rem 0.75rem;
    background: var(--global-card-bg-color);
  }
  .co-reading-case--warm {
    border-top-color: #c8857d;
  }
  .co-reading-case-label {
    margin: 0 0 0.75rem;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }
  .co-reading-case h4 {
    margin: 0 0 0.5rem;
    font-size: clamp(1.5rem, 4vw, 2rem);
    font-weight: 700;
    line-height: 1.25;
  }
  .co-reading-case-author {
    margin: 0 0 1.25rem;
  }
  .co-reading-case-route {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 0.5rem 0.75rem;
    margin: 0;
    font-size: 0.9rem;
    font-weight: 600;
  }
  .co-reading-case-swatch {
    display: inline-block;
    width: 3rem;
    height: 1rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 999px;
    background: linear-gradient(to right, #4e6663 60%, #8bc4a6 60%);
  }
  .co-reading-case--warm .co-reading-case-swatch {
    background: linear-gradient(to right, #ffe2aa 60%, #c8857d 60%);
  }
  .co-reading-case--deep {
    border-top-color: #571923;
  }
  .co-reading-case--deep .co-reading-case-swatch {
    background: linear-gradient(to right, #571923 60%, #a18f89 60%);
  }
---

<div class="co-reading-tag" title="Reading together — 함께 읽기, written as it sounds in Korean">
  <span>hamkke ilkgi</span><span aria-hidden="true">·</span><span lang="ko">함께 읽기</span>
</div>

**Co-Reading with AI** explores how humans and artificial intelligence can share a literary text and participate in the construction of meaning. Developed through my master’s thesis, the project translates emotions in modern Korean poetry into two-color palettes, creating an environment where readers can encounter, question, and reinterpret computational readings through color.

I independently developed the KCoEM dataset, emotion-to-color transformation algorithm, Co-Reading framework, and web interface. The research builds on the KPoEM dataset and emotion classification model developed collaboratively with Haein Ji and Byungjun Kim.

<p style="display: flex; flex-wrap: wrap; gap: 0.75rem;">
  <a class="co-reading-interface-link" href="https://poet-developer.github.io/KPoEMInterface/">Explore the interface · 한국어 →</a>
  <a class="co-reading-interface-link" href="https://poet-developer.github.io/KI_en/">Explore the interface · English →</a>
</p>

[📄Read the thesis]({{ '/assets/pdf/M-A-Thesis.pdf' | relative_url }}) · [📂Co-Reading code](https://github.com/poet-developer/Co-Reading) · [📡Interface code](https://github.com/poet-developer/KPoEMInterface)

## Thesis Committee

- **Committee Chair:** [Professor Dongsoo Suh](https://hicoda.hongik.ac.kr/post-professors/%EC%84%9C%EB%8F%99%EC%A3%BC/) (서동수)
- **Committee Member:** [Professor Baro Kim](https://digitalhumanities.kr/members/Baro.html) (김바로)
- **Thesis Advisor:** [Professor Byungjun Kim](https://digitalhumanities.kr/members/Byungjun.html) (김병준)

## Author’s Note

Much research on generative AI and creativity has focused on what machines can produce, leaving human experience, context, and interpretive agency at the margins. Through Co-Reading, I explore how humans and AI can inhabit a shared environment for reading and making meaning. By translating emotions in modern Korean poetry into color and bringing close reading, distant reading, and Co-Reading into an interface, this project experiments with ways to expand the experience of literary interpretation. I see the human task in the age of AI as designing environments in which we actively participate in interpretation and the construction of new meanings. Co-Reading is an experimental model for this coexistence, open to further refinement and to the development of interface-based data visualization as a field of aesthetic and media inquiry.

## Abstract

This study proposes a “Co-Reading” system as an environment in which humans and artificial intelligence collaboratively interpret literary texts. To achieve this goal, this study reconceptualizes datasets as environmental media that mediate interpretation between humans and AI. It also redefines AI as a “co-reader” that participates in the construction of meaning alongside humans. To implement such an interpretive environment, this study focuses on poetry, a literary genre characterized by interpretive ambiguity and multiplicity. Furthermore, recognizing color as an expressive element that mediates emotions and imagery in poetry, this study designed and developed a human–AI Co-Reading system that visualizes the emotions embedded in poetry through color.

First, this study constructed KPoEM （Korean Poetry Emotion Mapping）, an emotion dataset that structures human interpretations of emotion in Korean modern poetry, and developed a KPoEM emotion classification model for poetic texts.

Second, based on existing studies in color psychology, this study constructed KCoEM （Korean Color Emotion Mapping）, a Korean color-emotion dataset, and developed an emotion-to-color transformation algorithm that incorporates emotional attributes and principles of color harmony.

Third, this study designed a Co-Reading system that reconstructs human emotional responses and AI interpretations of an input poetic text into a two-color palette through context engineering. To realize this process, the communication structure and pipeline of the Co-Reading system were designed and implemented.

Fourth, using the KPoEM dataset, this study realized close reading, distant reading, and co-reading based on human–AI interaction as three independent reading environments and integrated them into a web-based interface prototype for comparative exploration. Whereas close reading and distant reading focus on providing microscopic and macroscopic perspectives on poetic texts, respectively, co-reading aims to encourage human sensory reinterpretation through color images reconstructed by humans and AI. Through this approach, this study suggests that data visualization can function as a communicative environment in which humans and AI collaboratively interpret texts and construct meaning.

Ultimately, this study experimentally implements a digital environment in which humans and AI collaboratively read the same literary text and construct new meanings through datasets and interfaces. Furthermore, it proposes one possible direction for a postwriting in an era where artificial intelligence increasingly mediates human knowledge and creativity.

## Reading as a Shared Interpretive Environment

The thesis asks two connected questions: **Can AI participate as a co-reader of literature? How can poetic emotion and imagery be visualized?** These questions place the reader’s interpretive experience at the center of the system’s design.

Drawing on reader-response theory, the thesis understands meaning as something realized through the encounter between a text and its reader. Poetry is especially suited to this inquiry because its metaphors, ambiguities, and sensory associations sustain multiple readings. A computational interpretation becomes another perspective that a human reader can engage with, reconsider, or contest.

<figure class="co-reading-figure">
  <img src="{{ '/assets/img/research/communication.png' | relative_url }}" alt="Communication structure connecting human-annotated emotion data and AI contextual interpretation through emotion–color visualization and a web interface." loading="lazy" style="display: block; width: 100%; max-width: 500px; height: auto; margin-left: auto; margin-right: auto;">
  <figcaption>Figure 1. The Co-Reading communication structure: human annotations and AI contextual interpretation meet in color visualization, returning to the reader through the interface.</figcaption>
</figure>

### LENS 01 : Datasets as Environmental Media

The project’s central proposition is that **a dataset can function as an environment for interpretation**. Annotation categories, word choices, and color associations record human judgments. They shape what an AI system can recognize and what a reader subsequently encounters through its outputs.

The thesis brings together McLuhan’s account of media, Peters’s understanding of media as environments, Manovich’s concept of the database as a cultural form, and Drucker’s account of data as *capta*: material selected and constituted through interpretation. These perspectives inform a design in which the dataset mediates a continuing exchange between human experience and machine interpretation.

In Co-Reading, this exchange follows a recursive path: human readings become structured emotion data; models and algorithms transform those records into color; readers encounter the palette and return to the poem with new associations. The visualization participates in meaning-making because its form influences how the poem is experienced.

### LENS 02 : AI as a Co-Reader

The term *co-reader* names AI’s interpretive role within this designed relationship. Its responses draw on human annotations, cultural conventions, and contextual instructions. Unexpected associations can invite a reader to notice an unfamiliar emotional possibility, while disagreement can prompt a closer return to the text.

The thesis approaches this as a conceptual and design experiment. It does not establish that AI experiences poetry as a human does. The reader’s situated response remains essential: a palette acquires literary significance through the act of reading it alongside the poem.

### LENS 03 : From Poetic Emotion to Color

**Poetic emotion emerges through imagery.** Drawing on Day-Lewis and Oh Kyu-won, the thesis describes metaphor, symbolism, and suggestion as ways of turning language into sensory experience. Images evoke emotional responses through the reader’s imagination, allowing several feelings to coexist within a passage. This relationship between language, imagery, and affect provides the basis for translating poetic emotion into another sensory medium.

**Color gives poetic imagery an emotional and cultural form.** The thesis discusses how colors evoke associations shaped by literary context and cultural experience—for example, the relationship between white imagery and Korean aesthetic sensibilities in readings of Jo Ji-hun’s poetry. Hue, brightness, and saturation contribute to the atmosphere a color conveys, while combinations of colors can intensify or transform that impression.

Co-Reading develops these relationships through a **two-color palette**. Pairing colors allows the system to express relationships between emotions, while adjustments to brightness and saturation reflect the poem’s contextual atmosphere. Emotion words and image adjectives connect poetic language to this visual composition, which readers can encounter as a sensory interpretation and bring back to their reading of the poem. The approach draws on the thesis’s discussions of poetic imagery and emotion (pp. 7–8) and poetry, color, and color combinations (pp. 12–14).

### LENS 04 : The Interface as an Environment for Humanistic Data Visualization

The interface is **a mediating space in which interpretation takes place**. Drawing on Drucker and Manovich, the thesis understands its arrangement and interactions as conditions that shape how readers encounter data and construct meaning. Co-Reading brings textual detail, emotional patterns, and color palettes into a shared environment, inviting readers to move between computational perspectives and their own sensory interpretations. Humanistic data visualization thus becomes an environment for experiencing and reconsidering meaning (pp. 5–6, 81–82, 97).

### Environmental Media : Construction Two Complementary Datasets

| Resource | Role in Co-Reading | Access |
| --- | --- | --- |
| **KPoEM — Korean Poetry Emotion Mapping** | The dataset contains 7,622 entries with expert annotations that preserve multiple emotional readings of poetic lines and works. It provides the foundation for the poetry-specific emotion classifier. | [Dataset DOI](https://doi.org/10.57967/hf/6303) · [Zenodo archive](https://zenodo.org/records/15598092) |
| **KCoEM — Korean Color Emotion Mapping** | A collection of 348 color records structures emotion–color associations from existing psychological experiments, Korean color literature, and color–emotion models, organized in relation to the KOTE emotion taxonomy. | [DOI Dataset](https://doi.org/10.5281/zenodo.21131097)|

### System Development : The Co-Reading Pipeline

<figure class="co-reading-figure">
  <img src="{{ '/assets/img/research/co-reading%20pipeline.png' | relative_url }}" alt="Co-Reading pipeline for transforming poetic emotion and contextual interpretation into color." loading="lazy" style="display: block; width: 100%; max-width: 500px; height: auto; margin-left: auto; margin-right: auto;">
  <figcaption>Figure 2. The Co-Reading pipeline for poetry–emotion–color transformation.</figcaption>
</figure>

The same poem enters two coordinated paths. The [KPoEM emotion classifier](https://doi.org/10.57967/hf/6301) identifies primary and secondary emotions, while an LLM interprets the poem’s context through a constrained vocabulary of image adjectives. The transformation algorithm combines these outputs.

| Step | Process | Interpretive function |
| --- | --- | --- |
| Emotion classification | Select the two highest-scoring emotions from the KPoEM model’s output. | Carry accumulated human annotations into the reading of a new text. |
| Hue selection | Search KCoEM using priority rules; apply analogous or contrasting color relationships according to emotional valence, with rules for neutral emotions and missing candidates. | Express relationships between the two emotions through color composition. |
| Contextual interpretation | Use context engineering to select an image adjective from the I.R.I image scale. | Introduce the poem’s atmosphere and imagery into palette construction. |
| Tone adjustment | Preserve the selected hues while adjusting saturation and brightness using the adjective-associated palette data. | Give similar emotion categories different visual atmospheres according to context. |
| Palette presentation | Display the resulting colors in a 6:4 area ratio. | Offer a sensory object that the reader can revisit alongside the poem. |

### Transformation : Poetry → Emotion → Color

<header class="co-reading-case">
  <p class="co-reading-case-label">Case study 01 · Shin Seok-jeong</p>
  <h4>In Your Eyes</h4>
  <p class="co-reading-case-author"><span lang="ko">신석정 · 네 눈망울에서는</span></p>
  <p class="co-reading-case-route"><span>Poetry</span><span aria-hidden="true">→</span><span>Pleased + Joy</span><span aria-hidden="true">→</span><span class="co-reading-case-swatch" aria-hidden="true"></span><span>Blue-green + Green</span></p>
</header>

The thesis follows an excerpt from Shin Seok-jeong’s *In Your Eyes* (네 눈망울에서는) through the pipeline. Its primary and secondary emotions lead to blue-green and green hues; the contextual adjective then guides their brightness and saturation. The example shows how a palette combines structured rules with contextual interpretation.

**Poetic input and contextual interpretation**

| Input poem excerpt (English translation) | AI-generated image adjective |
| --- | --- |
| From your eyes comes the scent<br>of green May<br>and white wild roses.<br><br>Your bright, shining eyes<br>hold within them<br>the stories of the stars. | Pure |

**Emotion classification results (Primary emotion / Secondary emotion)**

| Rank | Emotion | Score |
| --- | --- | --- |
| 1 | Pleased (Cute / Pretty) | 0.97 |
| 2 | Joy | 0.89 |

**Emotion-to-color mapping**

| Role | Selected emotion | Base hue |
| --- | --- | --- |
| Primary | Pleased (Cute / Pretty) | Blue Green |
| Secondary | Joy | Green |

<figure class="co-reading-figure" aria-label="Illustrative two-color palette: a muted blue-green primary color and a soft green secondary color, shown in a six-to-four ratio.">
  <div style="display: grid; grid-template-columns: 3fr 2fr; max-width: 640px; margin: 1.5rem auto 0.75rem; gap: 0.4rem 0;">
    <div>Primary color · Blue-green</div>
    <div>Secondary color · Green</div>
    <div style="height: 140px; background-color: #cbd8d7ff;" aria-hidden="true"></div>
    <div style="height: 140px; background-color: #e0f9ecff;" aria-hidden="true"></div>
  </div>
  <figcaption>Figure 3. “Pure,” combining Pleased (Cute / Pretty) and Joy. Values and colors are placeholders pending verification.</figcaption>
</figure>

In addition to “Pure,” the LLM also selected “Sensuous” during image-adjective selection. Even with the same blue-green and green base hues, these different interpretations can lead to different brightness and saturation adjustments, producing palettes with distinct sensory atmospheres. In Co-Reading, the AI’s interpretation of the poetic text thus serves as a central mediator in dynamically composing the color palette.

<figure class="co-reading-figure" aria-label="Illustrative Sensuous two-color palette: a dark muted blue-green primary color and a soft green secondary color, shown in a six-to-four ratio.">
  <div style="display: grid; grid-template-columns: 3fr 2fr; max-width: 640px; margin: 1.5rem auto 0.75rem; gap: 0.4rem 0;">
    <div>Primary color · Blue-green</div>
    <div>Secondary color · Green</div>
    <div style="height: 140px; background-color: #4e6663ff;" aria-hidden="true"></div>
    <div style="height: 140px; background-color: #8bc4a6ff;" aria-hidden="true"></div>
  </div>
  <figcaption>Figure 4. “Sensuous,” combining Pleased (Cute / Pretty) and Joy. Values and colors are placeholders pending verification.</figcaption>
</figure>

<header class="co-reading-case co-reading-case--warm">
  <p class="co-reading-case-label">Case study 02 · Baek Seok</p>
  <h4>Me, Natasha, and the White Donkey</h4>
  <p class="co-reading-case-author"><span lang="ko">백석 · 나와 나타샤와 흰 당나귀</span></p>
  <p class="co-reading-case-route"><span>Poetry</span><span aria-hidden="true">→</span><span>Pleased + Caring</span><span aria-hidden="true">→</span><span class="co-reading-case-swatch" aria-hidden="true"></span><span>Orange + Red</span></p>
</header>

**Poetic input and contextual interpretation**

| Input poem excerpt (English translation) | AI-generated image adjective |
| --- | --- |
| Snow falls thick and deep.<br> Beautiful Natasha loves me,<br> and somewhere a white donkey, delighted by tonight, will bray aloud.| Lovely |

**Emotion classification results (Primary emotion / Secondary emotion)**

| Rank | Emotion | Score |
| --- | --- | --- |
| 1 | Pleased (Cute / Pretty) | 0.95 |
| 2 | Caring | 0.93 |

**Emotion-to-color mapping**

| Role | Selected emotion | Base hue |
| --- | --- | --- |
| Primary | Pleased (Cute / Pretty) | Orange |
| Secondary | Caring | Red |

<figure class="co-reading-figure" aria-label="Two-color palette: a pale warm orange primary color and a muted red secondary color, shown in a six-to-four ratio.">
  <div style="display: grid; grid-template-columns: 3fr 2fr; max-width: 640px; margin: 1.5rem auto 0.75rem; gap: 0.4rem 0;">
    <div>Primary color · Orange</div>
    <div>Secondary color · Red</div>
    <div style="height: 140px; background-color: #ffe2aa;" aria-hidden="true"></div>
    <div style="height: 140px; background-color: #c8857d;" aria-hidden="true"></div>
  </div>
  <figcaption>Two-color palette conversion: “lovely,” combining Pleased (Cute / Pretty) and caring. Colors are approximated from the reference image.</figcaption>
</figure>

<header class="co-reading-case co-reading-case--deep">
  <p class="co-reading-case-label">Case study 03 · Kim Su-yeong</p>
  <h4>The Blue Sky</h4>
  <p class="co-reading-case-author"><span lang="ko">김수영 · 푸른 하늘을</span></p>
  <p class="co-reading-case-route"><span>Poetry</span><span aria-hidden="true">→</span><span>Regret / Disappointment + Sadness</span><span aria-hidden="true">→</span><span class="co-reading-case-swatch" aria-hidden="true"></span><span>Red + Orange</span></p>
</header>

**Poetic input and contextual interpretation**

| Input poem excerpt (English translation) | AI-generated image adjective |
| --- | --- |
| Anyone who has ever taken flight<br>
for freedom will know.<br>what the skylark sees <br>when it sings,<br>why the scent of blood<br>is mingled with freedom,<br>and why revolution<br>is a lonely thing. | Deep (깊은) |

*English translation prepared for this example from the Korean excerpt in the reference table.*

**Emotion classification results (Primary emotion / Secondary emotion)**

| Rank | Emotion | Score |
| --- | --- | --- |
| 1 | pitifulness/disappointment (안타까움 / 실망) | 0.94 |
| 2 | Sadness (슬픔) | 0.88 |

**Emotion-to-color mapping**

| Role | Selected emotion | Base hue |
| --- | --- | --- |
| Primary | pitifulness/disappointmen | Red |
| Secondary | Sadness | Orange |

<figure class="co-reading-figure" aria-label="Two-color palette: a dark burgundy primary color and a muted grayish orange secondary color, shown in a six-to-four ratio.">
  <div style="display: grid; grid-template-columns: 3fr 2fr; max-width: 640px; margin: 1.5rem auto 0.75rem; gap: 0.4rem 0;">
    <div>Primary color · Red</div>
    <div>Secondary color · Orange</div>
    <div style="height: 140px; background-color: #571923;" aria-hidden="true"></div>
    <div style="height: 140px; background-color: #a18f89;" aria-hidden="true"></div>
  </div>
  <figcaption>Two-color palette conversion: “Deep,” combining Regret / pitifulness/disappointmen. Emotion scores and base hues follow the reference table; colors are approximated from its palette.</figcaption>
</figure>

## Interface Application : Three Reading Environments

The web prototype brings **close reading, distant reading, and Co-Reading** into a shared interface. Each mode offers a different way of encountering the same literary material.

<p style="display: flex; flex-wrap: wrap; gap: 0.75rem;">
  <a class="co-reading-interface-link" href="https://poet-developer.github.io/KPoEMInterface/">Explore the interface · 한국어 →</a>
  <a class="co-reading-interface-link" href="https://poet-developer.github.io/KI_en/">Explore the interface · English →</a>
</p>

<figure class="co-reading-figure">
  <img src="{{ '/assets/img/research/kpoem_interface.png' | relative_url }}" alt="Backend data processing and AI inference connected to frontend close reading, distant reading, and Co-Reading interfaces." loading="lazy" style="display: block; width: 100%; max-width: 500px; height: auto; margin-left: auto; margin-right: auto;">
  <figcaption>Figure 5. System architecture of the KPoEM web interface, connecting data processing and AI inference with three reading environments.</figcaption>
</figure>


| Reading mode | Interface experience | Emphasis |
| --- | --- | --- |
| **Close reading** | Select a poetic line and inspect the emotion tags assigned by individual annotators. | Differences and overlaps in readings of a particular passage. |
| **Distant reading** | Explore aggregated emotion distributions and work–emotion heatmaps. | Patterns across works and a poet’s corpus. |
| **Co-Reading** | Select a poem, read its text, request a reading, and explore a two-color palette and its color information. | Sensory reinterpretation through the interaction of text, data, and AI. |

The thesis presents a static web prototype that demonstrates these reading modes and their interaction structure. In the Co-Reading view, selecting a work, reading the text, encountering the “Reading…” state, and receiving a palette form a deliberate temporal sequence. The interface invites attention to interpretation as a process, with opportunities to reset, compare, and read again.

## Contribution and Reflection

The project transforms human emotion data into **environmental media for sensory experience**. By translating poetic emotions into color, it invites readers to experience poetry through both reading and seeing, opening a cross-sensory dimension of literary reception. The dataset becomes a visual medium through which human interpretations can be encountered and reconsidered.

The web interface brings this perspective into practice by integrating close reading, distant reading, and Co-Reading. It frames **visualization as a condition for interpretation**, allowing readers to experience how meaning takes shape through interactions among texts, datasets, humans, and AI. Within this environment, AI takes the role of a **co-reader**, participating in the construction of meaning. Co-Reading can thus be understood as a form of *postwriting*: literary texts are reconfigured across data and visual media, and further meanings emerge through readers’ engagement.

The framework could extend to fiction, essays, and other cultural texts through connections with different language models and external data resources. Its current scope remains limited by the poetry corpus, culturally situated emotion–color mappings, and the interface’s influence on attention. Further user studies are needed to examine how this shared interpretive environment shapes literary experience.

## Note

Co-Reading builds on the [KPoEM Dataset & Emotion Classification Model]({% link _projects/1_project.md %}). The same foundational resources also support the related [RAG-Based Poetry Generation in Korean Modern Poetry]({% link _projects/2_project.md %}) project. The thesis develops their application to emotion–color transformation and a human–AI reading environment.

This research was supported by the Ministry of Education of the Republic of Korea and the National Research Foundation of Korea (NRF-2025S1A5B5A20019820).

## Publication

Lim, Iro. 2026. *Co-Reading with AI: Color Visualization of Emotion Data in Korean Modern Poetry.* Master’s thesis in Cultural Informatics, The Graduate School of Korean Studies, The Academy of Korean Studies. Advisor: Byungjun Kim. [Full thesis (PDF)]({{ '/assets/pdf/M-A-Thesis.pdf' | relative_url }}).

This summary draws on the thesis’s introduction (pp. 1–18), KCoEM and emotion–color algorithm chapters (pp. 40–63), system and interface design (pp. 64–95), and conclusion (pp. 96–98).

Related collaborative publication: Lim, Iro, Haein Ji, and Byungjun Kim. 2026. “KPoEM: A Human-Annotated Dataset for Emotion Classification and RAG-Based Poetry Generation in Korean Modern Poetry.” *The Review of Korean Studies* 29 (1): 161–206. [DOI: 10.25024/review.2026.29.1.006](https://doi.org/10.25024/review.2026.29.1.006).

## References

The following presentations document the development of KPoEM, the Co-Reading framework, and the interpretive interface.

- **DH2026 · Alliance of Digital Humanities Organizations (ADHO)** — July 29, 2026, Daejeon, Republic of Korea. Iro Lim and Byungjun Kim. “KPoEM: Visualizing Emotion Data in Modern Korean Poetry through a Web-Based Interpretive Interface.” First-author presentation. [DOI: 10.5281/zenodo.21779517](https://doi.org/10.5281/zenodo.21779517).

- **HKADH 2026 · Hong Kong Association for Digital Humanities** — January 23, 2026, The Chinese University of Hong Kong, Hong Kong. Iro Lim and Byungjun Kim. “Co-Reading: A Human–AI Co-Reader Media System for Poetry–Emotion–Color.” First-author poster presentation. [DOI: 10.5281/zenodo.18753718](https://doi.org/10.5281/zenodo.18753718).

- **Chung-Ang University Center for Cinema and Media Studies Graduate Student Conference** — December 2025, Seoul, Republic of Korea. Iro Lim. “An Environmental Turn in Datasets: Korean Modern Poetry–Emotion–Color Multimodal Media through Human–AI Co-Reading.” Sole-author presentation at “Unfamiliar Boundaries of Film and Media, Mediating Research.” [DOI: 10.5281/zenodo.17850832](https://doi.org/10.5281/zenodo.17850832).

- **180th Conference of the Bangyo Language and Literature Society** — October 18, 2025, Sungkyunkwan University, Seoul, Republic of Korea. Iro Lim, Haein Ji, and Byungjun Kim. “Emotion Analysis of Modern Korean Poetry and Its Application to AI Poetry Generation: Construction and Use of the KPoEM Dataset.” First-author presentation. [DOI: 10.5281/zenodo.18752999](https://doi.org/10.5281/zenodo.18752999).

- **Digital Humanities and Social Sciences Korea Conference** — April 25, 2025, James Joo-Jin Kim Center for Korean Studies, University of Pennsylvania, Philadelphia, USA. Iro Lim, Haein Ji, and Byungjun Kim. “Decoding the Poetic Language of Emotion in Korean Modern Poetry: Insights from a Human-Labeled Dataset and AI Modeling.” First-author presentation. [DOI: 10.5281/zenodo.18752715](https://doi.org/10.5281/zenodo.18752715).

- **2nd Korean Modern Literature Scholars Conference** — February 13, 2025, Sungkyunkwan University, Seoul, Republic of Korea. Iro Lim, Haein Ji, and Byungjun Kim. “Constructing an Emotion-Labeled Dataset of Modern Korean Poetry: A Foundational Study for Computational Emotion Classification and Generative AI Applications in Literary Texts.” First-author poster presentation. [DOI: 10.5281/zenodo.15055795](https://doi.org/10.5281/zenodo.15055795).
