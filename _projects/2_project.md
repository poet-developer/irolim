---
layout: page
title: RAG-Based Poetry Generation in Korean Modern Poetry
description: "Retrieval Augmented Generation (RAG) · Poetry Generation · AI creation"
img: ""
importance: 2
category: work
research_status: completed
research_years: "2024–2026"
giscus_comments: false
---

This project explores how Retrieval-Augmented Generation (RAG) can support Korean poetry writing through both semantic context and emotional alignment. It combines the KPoEM poetry dataset, a poetry-specific emotion classifier, and a Korean large language model to generate poems informed by the imagery and affective tone of an input poem.

I am the first author of this research, co-authored with Haein Ji and Byungjun Kim. The project connects structured literary data with generative AI, using expert-annotated poetic emotions to guide retrieval and prompt construction.

[Read the paper]({{ '/assets/pdf/RKS.pdf' | relative_url }}) · [Dataset](https://doi.org/10.57967/hf/6303) · [Emotion Classification Model](https://doi.org/10.57967/hf/6301) · [Code](https://github.com/AKS-DHLAB/KPoEM)

## Emotion-Aware Poetry Generation

The framework treats the input poem as a source of imagery, themes, and emotional cues. Two parallel processes connect it to the KPoEM corpus: semantic retrieval finds related poetic expressions, while emotion classification identifies an affective profile across **44 emotion categories**. These signals are combined to select the context supplied to the generative model.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/research/rks.jpg" title="Emotion-aware RAG-based poetry generation architecture" alt="An input poem feeds semantic retrieval from the KPoEM vector database and emotion classification. Emotion-constrained filtering selects ten contexts, which are combined with the input and emotion scores in a prompt for LLM poetry generation." class="img-fluid rounded d-block mx-auto" width="auto" max-width="min(100%, 800px)" max-height="800px" %}
    </div>
</div>
<div class="caption">
    Figure 1. Emotion-aware RAG-based poetry generation architecture. Semantic retrieval selects 100 candidate poetic units from the KPoEM vector database; emotion-constrained filtering narrows them to ten. The input poem, retrieved contexts, and emotion scores then guide prompt construction and LLM generation. Source: Figure 1 in the paper, p. 180.
</div>

### Building a Literary Vector Database

The retrieval corpus contains KPoEM’s line- and work-level texts. Each poetic unit is embedded using **KcELECTRA** and stored with poet metadata and emotion scores derived from five expert annotators. Scores are min–max normalized to the 0–1 range, retaining emotion categories with values of at least 0.2.

The vectors are indexed with **FAISS** and connected to the generation pipeline through **LangChain**. This gives the language model access to a specialized collection of Korean poetic expressions, with emotional information attached to each retrievable text.

### From Semantic Similarity to Emotional Alignment

Retrieval proceeds in two stages, using the emotion classifier’s output as a reference for selecting context:

| Stage | Method | Output |
| --- | --- | --- |
| Input analysis | The KPoEM classifier scores the input poem across 44 emotion categories. | An emotion profile for the input. |
| Semantic retrieval | Cosine similarity compares the input embedding with poetic units in the vector database. | The 100 most semantically similar candidates. |
| Emotion-constrained filtering | Candidate emotion metadata is compared with the input’s emotion scores. | Ten contexts selected for semantic relevance and emotional alignment. |

This filtering step is intended to reduce irrelevant context while retaining expressions suited to the input’s emotional tone. For example, the paper’s analysis of Kim Chunsu’s *Kkot* (Flower) identifies care (0.90), realization (0.87), and admiration (0.86) as its highest-scoring emotions. These scores help guide the selection of related poetic units.

## Prompt Design and Generation

The final prompt brings together **the input poem, ten retrieved poetic units, and the input’s emotion scores**. Each component has a distinct role: the source poem supplies conceptual imagery, the retrieved texts offer examples of diction and expression, and the emotion profile guides the tone.

The instructions ask the model to write a titled poem in Korean, draw inspiration from the retrieved expressions without copying them, and return only the poem. The prompt template is documented in Appendix B of the paper.

Generation uses **Midm-2.0-Base-Instruct**, with LangChain dynamically inserting the retrieved context and emotional information. The reported configuration uses a temperature of 0.7, top-p of 0.9, a maximum of 128 new tokens, and a repetition penalty of 1.2. The generative component is an LLM supplied with retrieved context and emotion guidance; the separately fine-tuned KPoEM model provides emotion classification.

### Generation Examples and Findings

The paper presents generation examples using poems by **Kim Chunsu, Kim Su-young, and Kim Hyesoon**, illustrating the framework across different poetic styles.

For Kim Chunsu’s *Kkot*, the generated poem, *The Moment I Call Your Name*, carries forward the source’s relationship between naming and the recognition of another’s existence. The paper discusses this continuity of imagery and emotional tone as an example of how retrieval and emotion guidance can shape generated poetry. Further examples use Kim Su-young’s *Sarang* (Love) and Kim Hyesoon’s *Nalgae hwansangtong* (Phantom Pain Wings).

#### Input and Generated Output

The following three examples reproduce the Korean input excerpts, generated poems, and English translations published in Tables 15–17 of the paper.

#### Kim Chunsu · Flower

<div class="row">
    <div class="col-md-6 mt-3">
        <h5>Input · 김춘수, 「꽃」 (excerpt)</h5>
        <blockquote lang="ko">
            <p>내가 그의 이름을 불러주기 전에는<br>
            그는 다만<br>
            하나의 몸짓에 지나지 않았다<br>
            <br>
            내가 그의 이름을 불러 주었을 때<br>
            그는 나에게로 와서<br>
            꽃이 되었다</p>
        </blockquote>
        <h6>English Translation · Input</h6>
        <blockquote lang="en">
            <p>Before I called his name<br>
            He was nothing more<br>
            But a mere gesture<br>
            <br>
            When I called his name<br>
            He came to me<br>
            And became a flower</p>
        </blockquote>
    </div>
    <div class="col-md-6 mt-3">
        <h5>Generated Output · 「이름 부르는 순간」</h5>
        <blockquote lang="ko">
            <p>나 그대를 부르기 이전엔<br>
            그저 스쳐가는 바람결이었네<br>
            수많은 얼굴 속 익명인 채<br>
            존재했지만 존재하지 않던<br>
            <br>
            그러나 한 글자 한 글자 마음 실어<br>
            당신의 이름을 부르니<br>
            어둠 속 별처럼 빛나기 시작하네<br>
            마침내 내게 다가와<br>
            영혼의 꽃송이 되어 피어오르네<br>
            <br>
            아껴주던 모든 것들이<br>
            이제 비로소 진짜 모습 드러내고<br>
            그리움 깊었던 시간들이<br>
            환영하는 눈빛 되어 돌아오네<br>
            <br>
            깊은 밤 홀로 서 있을 때조차<br>
            누군가 알아봐 준다는 안도감<br>
            그것은 곧 삶의 의미이며<br>
            세상을 살아갈 이유였구나</p>
        </blockquote>
        <h6>English Translation · The Moment I Call Your Name</h6>
        <blockquote lang="en">
            <p>Before I called your name<br>
            You were merely a passing breeze<br>
            Anonymous amidst countless faces<br>
            Existing, yet not truly existing<br>
            <br>
            But as I called your name<br>
            With each syllable laden with my heart<br>
            You began to shine like a star in the darkness<br>
            Finally, you come to me<br>
            And bloom as a flower of the soul<br>
            <br>
            All the things I cherished<br>
            Now finally reveal their true forms<br>
            And the times of deep longing<br>
            Return as eyes filled with welcome<br>
            <br>
            Even when standing alone in the deep night<br>
            The relief that someone recognizes me—<br>
            That was the very meaning of life<br>
            And the reason to live in this world</p>
        </blockquote>
    </div>
</div>
<div class="caption">
    Source: Table 15, pp. 184–185. Korean output generated by the RAG pipeline using Midm-2.0-Base-Instruct. English translations of both the input and generated poem are reproduced from the paper; they were produced using Google’s Gemini 3 Pro and subsequently reviewed and validated by the authors (p. 181, note 14).
</div>

#### Kim Su-young · Love

<div class="row">
    <div class="col-md-6 mt-3">
        <h5>Input · 김수영, 「사랑」 (excerpt)</h5>
        <blockquote lang="ko">
            <p>어둠 속에서도 불빛 속에서도 변치 않는<br>
            사랑을 배웠다 너로 해서<br>
            <br>
            그러나 너의 얼굴은<br>
            어둠에서 불빛으로 넘어가는<br>
            그 찰나에 꺼졌다 살아났다<br>
            너의 얼굴은 그만큼 불안하다</p>
        </blockquote>
        <h6>English Translation · Input</h6>
        <blockquote lang="en">
            <p>Unchanging in the dark and in the light,<br>
            I learned love through you<br>
            But your face,<br>
            passing from darkness to light,<br>
            flickered out and came alive in that fleeting moment<br>
            Your face is that precarious</p>
        </blockquote>
    </div>
    <div class="col-md-6 mt-3">
        <h5>Generated Output · 「밤길의 약속」</h5>
        <blockquote lang="ko">
            <p>밤하늘 별들이 하나둘 떨어져<br>
            그대와 나누었던 그 순간처럼<br>
            어둠과 빛 사이 경계에서<br>
            얼굴마저 흐릿해지네<br>
            <br>
            불안한 눈동자 안에 담긴<br>
            깊은 한숨 같은 그리움이여<br>
            <br>
            서로 다른 길 위에 서서<br>
            보이지 않아도 느낄 수 있는<br>
            변하지 않을 마음 하나<br>
            <br>
            불빛 깜빡이며 사라지는<br>
            그 짧은 찰나가 주는 아픔을<br>
            그래도 견뎌내는 것이 우리였기에<br>
            <br>
            별똥별 지나며 흩어진 조각마다<br>
            다시 만나자던 그 약속<br>
            잊혀진 듯하지만 잊혀지지 않은<br>
            그리움이란 이름으로 남아있어</p>
        </blockquote>
        <h6>English Translation · Promise on a Night Road</h6>
        <blockquote lang="en">
            <p>Stars in the night sky fall one by one,<br>
            Just like that moment I shared with you.<br>
            At the boundary between darkness and light,<br>
            Even your face grows faint<br>
            <br>
            Oh, this longing like a deep sigh,<br>
            Held within anxious eyes<br>
            <br>
            Standing on different paths,<br>
            Though unseen, we can feel<br>
            This one unchanging heart<br>
            <br>
            The pain of that brief, fleeting moment<br>
            As the light flickers and fades—<br>
            Because enduring it was who we were<br>
            <br>
            In every scattered fragment of a passing shooting star,<br>
            The promise we made to meet again<br>
            Seems forgotten, yet is never forgotten,<br>
            Remaining under the name of longing</p>
        </blockquote>
    </div>
</div>
<div class="caption">
    Source: Table 16, pp. 185–186. Korean output generated by the RAG pipeline using Midm-2.0-Base-Instruct. English translations of both the input and generated poem are reproduced from the paper; they were produced using Google’s Gemini 3 Pro and subsequently reviewed and validated by the authors (p. 181, note 14).
</div>

#### Kim Hyesoon · Phantom Pain Wings

<div class="row">
    <div class="col-md-6 mt-3">
        <h5>Input · 김혜순, 「날개 환상통」 (excerpt)</h5>
        <blockquote lang="ko">
            <p>하이힐을 신은 새 한마리<br>
            아스팔트 위를 울면서 간다<br>
            <br>
            마스카라는 녹아 흐르고<br>
            밤의 깃털은 무한대 무한대<br>
            <br>
            그들은 말했다<br>
            애도는 우리 것<br>
            너는 더러워서 안 돼</p>
        </blockquote>
        <h6>English Translation · Input</h6>
        <blockquote lang="en">
            <p>A bird in high heels<br>
            goes crying across the asphalt<br>
            <br>
            Mascara melting and running down,<br>
            the night’s feathers are infinite, infinite<br>
            <br>
            They said<br>
            Mourning is ours<br>
            You cannot, for you are dirty</p>
        </blockquote>
    </div>
    <div class="col-md-6 mt-3">
        <h5>Generated Output · 「밤의 새들」</h5>
        <blockquote lang="ko">
            <p>하이힐 신겨진 발소리 아스팔트 위로<br>
            눈물방울들이 흘러내려<br>
            무수한 별들이 떨어진 자리마다<br>
            새들은 울음 섞인 노래를 부른다<br>
            <br>
            마스카라 번지는 눈가엔 꿈도 함께 번져<br>
            무한히 이어지는 어둠 속에서 길을 잃고<br>
            누군가 던진 차가운 목소리가 메아리친다<br>
            <br>
            ‘더러워서 너는 안된다’<br>
            그 한마디에 날개 꺾인 채 주저앉으며<br>
            새벽까지 걸어가는 그 발걸음 소리<br>
            <br>
            도시의 불빛 사이로 스며드는 달빛처럼<br>
            희망이란 작은 씨앗 하나 품고 있지만<br>
            가슴 깊은 곳에선 여전히 울고 있는<br>
            밤의 깃털들을 나는 바라본다</p>
        </blockquote>
        <h6>English Translation · Birds of the Night</h6>
        <blockquote lang="en">
            <p>The sound of high-heeled footsteps upon the asphalt,<br>
            Teardrops flowing down<br>
            Wherever countless stars have fallen,<br>
            The birds sing a song laced with weeping<br>
            <br>
            Around eyes where mascara smudges, dreams smudge too<br>
            Lost in the infinitely stretching dark,<br>
            A cold voice cast by someone echoes<br>
            <br>
            “You cannot, for you are dirty.”<br>
            Sinking down with broken wings at that single word,<br>
            The sound of those footsteps pacing until dawn<br>
            <br>
            Like moonlight seeping through the city lights,<br>
            Though harboring a tiny seed called hope,<br>
            I gaze at the feathers of the night<br>
            That are still weeping deep within</p>
        </blockquote>
    </div>
</div>
<div class="caption">
    Source: Table 17, pp. 186–187. Korean output generated by the RAG pipeline using Midm-2.0-Base-Instruct. English translations of both the input and generated poem are reproduced from the paper; they were produced using Google’s Gemini 3 Pro and subsequently reviewed and validated by the authors (p. 181, note 14).
</div>

These are qualitative demonstrations of the pipeline. They illustrate how the system draws on poetic context and emotion metadata, rather than establishing a quantitative improvement in generation quality. The retrieval corpus is drawn from five poets, which also limits the range of voices and historical contexts available to the generator.

## Note

This research builds on the [KPoEM Dataset & Emotion Classification Model]({% link _projects/1_project.md %}). The dataset supplies the retrieval corpus and expert-annotated emotion metadata, while the classifier provides the input poem’s emotion profile. Together, they form the foundation for the RAG poetry generation pipeline described here.

## Publication

Lim, Iro, Haein Ji, and Byungjun Kim. 2026. “KPoEM: A Human-Annotated Dataset for Emotion Classification and RAG-Based Poetry Generation in Korean Modern Poetry.” *The Review of Korean Studies* 29 (1): 161–206. [DOI: 10.25024/review.2026.29.1.006](https://doi.org/10.25024/review.2026.29.1.006).

This project summary focuses on the RAG framework and generation examples, drawing on pp. 180–188 and Appendix B (pp. 204–206). [Full paper (PDF)]({{ '/assets/pdf/RKS.pdf' | relative_url }}).

## References

Earlier stages of this research were presented at the following conferences:

- **180th Conference of the Bangyo Language and Literature Society (반교어문학회 제180차 정기학술대회)** — October 18, 2025, Sungkyunkwan University, Seoul. Iro Lim, Haein Ji, and Byungjun Kim. “Emotion Analysis of Modern Korean Poetry and Its Application to AI Poetry Generation: Construction and Use of the KPoEM Dataset.” First-author presentation. [DOI: 10.5281/zenodo.18752999](https://doi.org/10.5281/zenodo.18752999).

- **Digital Humanities and Social Sciences Korea Conference** — April 25, 2025, James Joo-Jin Kim Center for Korean Studies, University of Pennsylvania, Philadelphia, USA. Iro Lim, Haein Ji, and Byungjun Kim. “Decoding the Poetic Language of Emotion in Korean Modern Poetry: Insights from a Human-Labeled Dataset and AI Modeling.” First-author presentation. [DOI: 10.5281/zenodo.18752715](https://doi.org/10.5281/zenodo.18752715).

- **2nd Korean Modern Literature Scholars Conference (제2회 한국현대문학자대회)** — February 13, 2025, Sungkyunkwan University, Seoul. Iro Lim, Haein Ji, and Byungjun Kim. “Constructing an Emotion-Labeled Dataset of Modern Korean Poetry: A Foundational Study for Computational Emotion Classification and Generative AI Applications in Literary Texts.” First-author poster presentation. [DOI: 10.5281/zenodo.15055795](https://doi.org/10.5281/zenodo.15055795).
