---
layout: page
title: Co-Reading with AI
description: ""
img:
importance: 1
category: work
research_status: completed
research_years: "2024-2026"
related_publications: false
_styles: |
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

<div class="co-reading-tag" title="Reading together — 함께 읽기, written as it sounds in Korean">
  <span>hamkke ilkgi</span><span aria-hidden="true">·</span><span lang="ko">함께 읽기</span>
</div>

**Co-Reading with AI** explores how humans and artificial intelligence can share a literary text and participate in the construction of meaning. Developed through my master’s thesis, the project translates emotions in modern Korean poetry into two-color palettes, creating an environment where readers can encounter, question, and reinterpret computational readings through color.

I independently developed the KCoEM dataset, emotion-to-color transformation algorithm, Co-Reading framework, and web interface. The research builds on the KPoEM dataset and emotion classification model developed collaboratively with Haein Ji and Byungjun Kim.

[Read the thesis]({{ '/assets/pdf/M-A-Thesis.pdf' | relative_url }}) · [Explore the interface](https://poet-developer.github.io/KPoEMInterface/) · [Co-Reading code](https://github.com/poet-developer/Co-Reading) · [Interface code](https://github.com/poet-developer/KPoEMInterface)

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

### Environmental Media : Two Complementary Datasets

| Resource | Role in Co-Reading | Access |
| --- | --- | --- |
| **KPoEM — Korean Poetry Emotion Mapping** | Expert annotations preserve multiple emotional readings of poetic lines and works. The dataset provides the foundation for the poetry-specific emotion classifier. | [Dataset DOI](https://doi.org/10.57967/hf/6303) · [Zenodo archive](https://zenodo.org/records/15598092) |
| **KCoEM — Korean Color Emotion Mapping** | A collection of 348 color records structures emotion–color associations from existing psychological experiments, Korean color literature, and color–emotion models, organized in relation to the KOTE emotion taxonomy. | [Thesis dataset DOI](https://doi.org/10.5281/zenodo.21131097)|

KCoEM makes the cultural and interpretive basis of color selection explicit. Its associations provide a situated resource for visual interpretation; the thesis also recognizes that some emotion categories have limited correspondence and that mappings incorporate human judgment.

### System : The Co-Reading Pipeline

The same poem enters two coordinated paths. The [KPoEM emotion classifier](https://doi.org/10.57967/hf/6301) identifies primary and secondary emotions, while an LLM interprets the poem’s context through a constrained vocabulary of image adjectives. The transformation algorithm combines these outputs.

| Step | Process | Interpretive function |
| --- | --- | --- |
| Emotion classification | Select the two highest-scoring emotions from the KPoEM model’s output. | Carry accumulated human annotations into the reading of a new text. |
| Hue selection | Search KCoEM using priority rules; apply analogous or contrasting color relationships according to emotional valence, with rules for neutral emotions and missing candidates. | Express relationships between the two emotions through color composition. |
| Contextual interpretation | Use context engineering to select an image adjective from the I.R.I image scale. | Introduce the poem’s atmosphere and imagery into palette construction. |
| Tone adjustment | Preserve the selected hues while adjusting saturation and brightness using the adjective-associated palette data. | Give similar emotion categories different visual atmospheres according to context. |
| Palette presentation | Display the resulting colors in a 6:4 area ratio. | Offer a sensory object that the reader can revisit alongside the poem. |

For example, the thesis follows an excerpt from Shin Seok-jeong’s *Ne nunmangureseoneun* through the pipeline. Its primary and secondary emotions lead to blue-green and green hues; the contextual adjective then guides their brightness and saturation. The example shows how a palette combines structured rules with contextual interpretation.

## Interface : Three Reading Environments

The web prototype brings **close reading, distant reading, and Co-Reading** into a shared interface. Each mode offers a different way of encountering the same literary material.

| Reading mode | Interface experience | Emphasis |
| --- | --- | --- |
| **Close reading** | Select a poetic line and inspect the emotion tags assigned by individual annotators. | Differences and overlaps in readings of a particular passage. |
| **Distant reading** | Explore aggregated emotion distributions and work–emotion heatmaps. | Patterns across works and a poet’s corpus. |
| **Co-Reading** | Select a poem, read its text, request a reading, and explore a two-color palette and its color information. | Sensory reinterpretation through the interaction of text, data, and AI. |

The thesis presents a static web prototype that demonstrates these reading modes and their interaction structure. In the Co-Reading view, selecting a work, reading the text, encountering the “Reading…” state, and receiving a palette form a deliberate temporal sequence. The interface invites attention to interpretation as a process, with opportunities to reset, compare, and read again.

## Contribution and Reflection

The project’s contribution is a working design for **visualization as a communicative environment**. Dataset construction, classification, color transformation, and interface design form one interpretive system. Its value lies in making the relationships among these choices available to literary experience.

The thesis connects this transformation to *postwriting*: poetic language is reorganized into data and visual form, and the reader’s engagement with that form becomes a further act of interpretation. Reading and making become linked through the reconstruction of an existing text across media.

The completed research establishes this conceptual framework, algorithm, and prototype. It also identifies limits: the poetry corpus covers a restricted group of poets, emotion–color mappings are uneven and culturally situated, and the interface itself directs attention. Further user studies are needed to evaluate how these interactions affect interpretation. These questions remain part of the project’s philosophical commitment to examining the conditions under which humans and AI read together.

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
