# Fake News Detection in TikTok Short-Form Videos

## Motivation

Short-form video platforms such as TikTok, YouTube Shorts, and Kuaishou have reshaped how people consume news and public information. Given the sheer volume of uploads, detection systems must be not only accurate but also computationally efficient [2]. Rich multimodal signals and highly optimized recommendation systems allow fake news short videos to attract massive attention before professional fact-checking becomes available, amplifying societal risks [2].

Compared to text-only fake news, short news videos are harder to analyze: manipulations may occur in any modality and at any granularity, and successful fakes rarely contain glaring artifacts in a single stream. Instead, they often exploit **cross-modal inconsistencies** — where each modality looks plausible alone but the joint message is misleading [2].

This project aims to **make fact-checking fun and future-proof** by teaching machines to _watch_, _listen_, and _read_ videos — just like we do — and figure out what's real and what's not.

---

### Dataset

This project will use a subset of the **FakeTT dataset**, a multimodal dataset designed for misinformation detection in English short-form videos [1]. FakeTT contains labeled samples collected from TikTok, each comprising the video, title, and associated metadata such as user profiles and engagement signals [1].

For training, validation, and testing, we will follow the **chronological split protocol**, using 70%/15%/15% of videos respectively [2]. This ensures temporal consistency and prevents data leakage from future posts into training data.

> **Team Size:** The scope of this project is large enough for a group of two, but it can be simplified for a single-person project as well.

---

## 🔎 Research Questions

1. **Claim Check:** Can we automatically extract factual claims from a video's speech, subtitles, and visuals?

2. **Text vs. Talk:** Do transcripts, captions, or on-screen text contribute more when spotting suspicious claims?

3. **Spot the Lie:** Can we detect when a video's visuals and text don't match (e.g., when the voice says one thing but the image shows another)? This is particularly relevant since fake news short videos often exploit cross-modal inconsistencies where each modality looks plausible alone but the joint message is misleading [2].

4. **Déjà Vu Detector:** Can we catch videos being reused in misleading ways?

5. **Fake Formula:** What patterns make fake videos go viral?

---

## 🛠️ Skills & Tools You'll Need

| Category | Examples |
|---|---|
| **Machine Learning & NLP** | Transformers, BERT, text classification |
| **Computer Vision** | Feature extraction, CLIP, OCR |
| **Multimodal ML** | Fusing text, audio, and visual modalities |
| **Programming & Frameworks** | Python, HuggingFace, PyTorch |
| **Research Methods** | Data annotation, evaluation metrics, experiment design |

---

## 📊 Suggested Approach

### Phase 1: Data Preparation
- Sample and preprocess a balanced subset from the FakeTT dataset [1]
- Extract video frames, audio transcripts, on-screen text (via OCR), and metadata (user profiles, engagement signals) [1]
- Apply the 70%/15%/15% chronological split for train/validation/test sets [2]

### Phase 2: Unimodal Baselines
- Train separate classifiers on **text-only**, **audio-only**, and **visual-only** features to answer Research Question 2
- Compare performance across modalities to understand which signals carry the most discriminative power

### Phase 3: Multimodal Fusion
- Combine modalities using late fusion, early fusion, or attention-based approaches
- Focus on detecting **cross-modal inconsistencies** — a key characteristic of fake news short videos where manipulations may occur in any modality and at any granularity [2]
- Address Research Question 3

### Phase 4: Claim Extraction & Verification
- Use NLP pipelines to extract factual claims from transcripts
- Compare against known fact-checks (Research Question 1)

### Phase 5: Virality & Pattern Analysis
- Analyze engagement metadata to identify what makes fake content spread (Research Question 5)
- Leverage the user profile and engagement signal data available in FakeTT [1]

---

## 📦 Deliverables

| Deliverable | Description |
|---|---|
| **Working Prototype** | A functional system capable of classifying TikTok-style videos as real or fake using multimodal signals |
| **Technical Report** | Documentation of methodology, experimental setup, results, and error analysis |
| **Ethics & Limitations Analysis** | Discussion of dataset biases, potential for misuse, responsible deployment considerations, and the societal risks of undetected misinformation [2] |
| **Final Presentation & Live Demo** | In-class demonstration with Q&A session |

---

## 📚 Key References

- **FakeTT** (Bu et al., 2024) — Multimodal dataset for misinformation detection in English short-form TikTok videos [1]
- **FVC** (Papadopoulou et al., 2019) — Multimodal dataset for fake news detection in real-world news videos, which can serve as a complementary benchmark [1]
