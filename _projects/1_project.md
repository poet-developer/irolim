---
layout: page
title: KPoEM Dataset & Emotion Classification Model
description: "Emotion Annotation · Literary NLP · Emotion Classification · Dataset Development · Computational Literary Studies"
importance: 3
category: work
research_status: completed
research_years: "2024–2026"
related_publications: false
---

KPoEM (Korean Poetry Emotion Mapping) combines an expert-annotated dataset of modern Korean poetry with an emotion classification model adapted to poetic language. The project addresses a central challenge in literary computing: emotions expressed through metaphor, imagery, and culturally specific language are difficult to capture with models trained on everyday text.

I am the first author of this research, co-authored with Haein Ji and Byungjun Kim. The project connects literary annotation with natural language processing to support quantitative analysis of poetic emotion.

[📄Read the paper]({{ '/assets/pdf/RKS.pdf' | relative_url }}) · [📁Dataset](https://doi.org/10.57967/hf/6303) · [📁Model](https://doi.org/10.57967/hf/6301) · [📁Code](https://github.com/AKS-DHLAB/KPoEM)

## Building the KPoEM Dataset

The corpus comprises **483 poems by five modern Korean poets**: Han Yong-un, Im Hwa, Kim So-wol, Yi Sang, and Yun Dong-ju. Texts were collected from Korean Wikisource, with poet selection guided by literary scholarship, public recognition, and the availability of public-domain works.

Preprocessing combined automated extraction with manual review. Markup was removed, text order and typographical errors were checked against source editions, and Hangul–Hanja notation was standardized while retaining poetic diction and older expressions. Duplicate lines were removed from the line-level data, while repetitions were preserved within complete works. Poems whose visual structures could not be adequately represented as text were excluded.


### Two Levels of Emotional Context

KPoEM contains **7,622 entries**, designed to capture both local expression and broader poetic context.

| Dataset | Entries | Annotation context |
| --- | ---: | --- |
| Line-level | 7,007 | Individual lines presented in shuffled order to examine emotion without neighboring lines. |
| Work-level | 615 | Poems read in full context, preserving line and stanza structure during annotation; texts longer than 512 characters segmented into ordered passages. |

The 615 work-level entries therefore represent segments from the corpus of 483 poems, rather than 615 distinct poems. Identifiers, titles, poet names, and individual annotator labels connect the textual units to their source works.

### Expert, Multi-Label Annotation

Five researchers trained in Korean literature and/or digital humanities independently annotated the texts using **44 emotion categories** adapted from KOTE. The taxonomy includes emotions such as sadness and joy alongside culturally significant categories such as *seoreoum* (서러움, sorrow) and *bijangham* (비장함, resolute), as well as a “NO EMOTION” label.

Annotators followed shared definitions and examples, completed line-level annotation before work-level annotation, and could assign up to ten labels to an entry. Keeping each annotator’s judgments preserves overlapping emotions and differences in interpretation instead of reducing a poem to one dominant category. At least three annotators shared at least one label for 92.52% of entries; this measures partial label overlap, rather than agreement on every assigned emotion.

## Developing the Emotion Classification Model

The classifier uses **KcELECTRA-base-v2022** with sequential fine-tuning: first on KOTE, a general-domain Korean emotion dataset of online comments, and then on KPoEM. This approach transfers general emotion recognition to the metaphorical and contextual language of poetry.

For each entry, labels from the five annotators were aggregated into a 44-dimensional vector of label frequencies. Per-entry min–max normalization converted these frequencies into soft multi-label targets, preserving relative agreement among annotators. The model was trained with binary cross-entropy loss across the 44 categories.

Line-level and work-level data were each split into training, validation, and test sets at an 8:1:1 ratio, then combined by split, yielding **6,096 training, 763 validation, and 763 test entries**. Hyperparameters were tuned with Optuna, and evaluation used a classification threshold of 0.30.

<!-- Future figure: sequential fine-tuning and soft-label construction diagram. -->
<div class="caption">
    Figure 3. Model development: KcELECTRA → KOTE fine-tuning → KPoEM fine-tuning, with normalized multi-annotator emotion vectors used as training targets.
</div>

### Results

| Fine-tuning data | Micro precision | Micro recall | Micro-F1 | Macro-F1 |
| --- | ---: | ---: | ---: | ---: |
| KOTE only | 0.49 | 0.38 | 0.43 | 0.34 |
| KPoEM only | 0.53 | 0.66 | 0.59 | 0.45 |
| **KOTE → KPoEM** | **0.53** | **0.69** | **0.60** | **0.49** |

Sequential fine-tuning achieved the highest micro- and macro-F1 scores among the three configurations. Compared with the KOTE-only baseline, micro-F1 increased from **0.43 to 0.60**, while micro recall rose from **0.38 to 0.69**. Direct fine-tuning on KPoEM already produced most of the micro-F1 gain; the sequential strategy added a smaller improvement and better macro-F1, which gives equal weight to each emotion category.

Together, the dataset and classifier provide a foundation for studying multiple, coexisting emotions in modern Korean poetry. The results demonstrate the value of expert literary annotation and domain adaptation within the evaluated corpus of five poets.

## Note

The KPoEM dataset and emotion classification model were developed as foundational resources for research on [RAG-based AI poetry generation]({% link _projects/2_project.md %}) and Iro Lim’s master’s thesis, <a href="https://poet-developer.github.io/irolim/projects/7_project/" style="color: var(--global-theme-color);"><em style="color: inherit;">Co-Reading with AI: Color Visualization of Emotion Data in Korean Modern Poetry</em></a>.

## Publication

Lim, Iro, Haein Ji, and Byungjun Kim. 2026. “KPoEM: A Human-Annotated Dataset for Emotion Classification and RAG-Based Poetry Generation in Korean Modern Poetry.” *The Review of Korean Studies* 29 (1): 161–206. [DOI: 10.25024/review.2026.29.1.006](https://doi.org/10.25024/review.2026.29.1.006).

This project summary covers dataset construction and emotion classification, drawing on pp. 168–180 and Appendix A (pp. 195–203). [Full paper (PDF)]({{ '/assets/pdf/RKS.pdf' | relative_url }}).


## References

Earlier stages of this research were presented at the following conferences:

- **180th Conference of the Bangyo Language and Literature Society (반교어문학회 제180차 정기학술대회)** — October 18, 2025, Sungkyunkwan University, Seoul. Iro Lim, Haein Ji, and Byungjun Kim. “Emotion Analysis of Modern Korean Poetry and Its Application to AI Poetry Generation: Construction and Use of the KPoEM Dataset.” First-author presentation. [DOI: 10.5281/zenodo.18752999](https://doi.org/10.5281/zenodo.18752999).

- **Digital Humanities and Social Sciences Korea Conference** — April 25, 2025, James Joo-Jin Kim Center for Korean Studies, University of Pennsylvania, Philadelphia, USA. Iro Lim, Haein Ji, and Byungjun Kim. “Decoding the Poetic Language of Emotion in Korean Modern Poetry: Insights from a Human-Labeled Dataset and AI Modeling.” First-author presentation. [DOI: 10.5281/zenodo.18752715](https://doi.org/10.5281/zenodo.18752715).

- **2nd Korean Modern Literature Scholars Conference (제2회 한국현대문학자대회)** — February 13, 2025, Sungkyunkwan University, Seoul. Iro Lim, Haein Ji, and Byungjun Kim. “Constructing an Emotion-Labeled Dataset of Modern Korean Poetry: A Foundational Study for Computational Emotion Classification and Generative AI Applications in Literary Texts.” First-author poster presentation. [DOI: 10.5281/zenodo.15055795](https://doi.org/10.5281/zenodo.15055795).
