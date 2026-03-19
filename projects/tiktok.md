# DAT560 Class Project: Multimodal Fake-News Detection on FakeTT

## 1) Project Title
**Improving Multimodal Fake-News Detection on FakeTT with Off-the-Shelf Models and Prompt Engineering**

---

## 2) Project Context and Motivation
Misinformation on short-video platforms is a high-impact societal challenge. The FakeTT dataset provides multimodal signals that make it an effective benchmark for fake-news detection.

This class project asks you to:
1. Reproduce a **strong baseline** using limited supervision. You may use the baseline here https://github.com/ICTMCG/FakingRecipe/tree/main
2. Build an **advanced system** centered on **off-the-shelf multimodal LLMs (MLLMs)**. You will be given access to one of the MLLMs on ollama server hosted on UiS servers.
3. Use **prompt engineering** (and optional fine-tuning) to improve over reported paper-style baselines on the provided subset.

The goal is not just model performance, but also rigorous experimentation, reproducibility, and scientific reasoning.

---

## 3) Data Source and Split Policy (Required)

Download the dataset from [here](https://ux.uis.no/~vsetty/data/video_sample.tgz).

Untar the tgz file with command in CLI `tar -xvzf video_sample.tgz`

Use this directory structure exactly:
- `video_sample/train/`
- `video_sample/val/`
- `video_sample/test/`

### Data usage rules
- You may use sampled **train/val** for:
  - prompt development,
  - few-shot in-context examples,
  - model calibration,
  - optional fine-tuning.
- You must evaluate final results on the sampled **test (50%)** only.
- Do not tune on the test set.

---

## 4) Core Deliverables

Each team must submit:
1. **Baseline run** (required)
2. **Advanced solution run** (required)
3. A final report with experimental evidence
4. Reproducible code and run instructions

---

## 5) Task Definition

### Primary task
Binary classification of fake-news content:
- **Label 1:** Fake / misleading
- **Label 0:** Real / non-misleading

### Inputs
Use all available modalities provided in the dataset package:
- Video frames (sampled clips or keyframes)
- Textual fields (title, OCR, ASR transcript, hashtags, description, comments)
- Metadata fields released with the dataset

---

## 6) Required System 1: Baseline

Implement the following baseline exactly:

1. Build a **text-only supervised classifier** using train/val.
2. Text input must concatenate available textual fields per sample.
3. Use either:
   - TF-IDF + Logistic Regression, or
   - RoBERTa-base with a linear classification head.
4. Select hyperparameters on validation only.
5. Report final metrics on test only.

### Baseline minimum requirements
- Clear preprocessing pipeline
- Explicit train/val procedure
- At least one hyperparameter setting justified
- Final test results on the 50% sampled test split

---

## 7) Required System 2: Advanced Multimodal LLM Solution

This is the central component of the project.

### Goal
Use one or more off-the-shelf multimodal LLMs and prompt engineering to outperform the baseline.

### Required advanced elements
1. **Prompt design strategy**
   - Role prompting (fact-checker, media forensics analyst)
   - Structured outputs (JSON with label + confidence + rationale)
   - Instruction constraints (evidence-first reasoning)

2. **Few-shot prompting**
   - Curate high-quality train/val exemplars
   - Compare 0-shot vs 1/3/5-shot

3. **Chain-of-verification style prompting**
   - Ask model to first identify claims, then cross-check internal consistency, then classify
   - Keep final output concise and machine-parseable

4. **Multimodal evidence decomposition**
   - Separate checks for visual cues vs textual cues
   - Late fusion at decision layer (rule-based, confidence-weighted, or learned)

5. **Self-consistency / ensemble prompting**
   - Multiple prompt variants or multiple model calls
   - Aggregate decisions via majority vote or confidence scoring

6. **Error-aware prompting loop**
   - Analyze val errors
   - Introduce targeted prompt modifications for known failure types

### Fine-tuning policy
Teams may fine-tune smaller models using:
- university GPUs, or
- their own compute resources.

Possible strategies:
- LoRA/QLoRA fine-tuning of text LLMs on extracted multimodal summaries
- Fine-tuning multimodal encoders/classifiers on train+val protocol
- Distillation: use MLLM outputs as soft labels to train a smaller deployable model

If you fine-tune, report:
- hardware and runtime,
- training budget,
- parameter count / trainable params,
- reproducibility seed(s).

---

## 8) Experimental Design Requirements

### Minimum experiments
You must report at least:
1. Baseline performance
2. Advanced MLLM performance
3. Ablation(s) showing what helped

### Required ablations
- No visual input vs visual+text input
- 0-shot vs few-shot
- Prompt template A vs B vs C
- Single-pass vs self-consistency voting
- With/without confidence threshold tuning on val

### Reproducibility checklist
- Fixed random seeds
- Exact sampled split files saved and versioned
- Prompt templates versioned in code or config
- Evaluation script deterministic and documented

---

## 9) Evaluation Metrics (Required)

Report the following on test (50% sample):
- Accuracy
- Precision
- Recall
- F1 score (macro and/or binary, specify clearly)
- Confusion matrix

If class imbalance exists, emphasize F1 and per-class performance.

Also include:
- Validation metrics for model selection
- Calibration/threshold selection procedure (if any)
- Statistical robustness (e.g., multiple seeds or bootstrap CI if feasible)

---

## 10) Improvement Requirement

Because this class uses a fixed sampled subset, improvement is defined as:
- outperforming your reproduced baseline and/or paper-inspired baseline on the same sampled setup,
- with transparent and fair comparisons.

You are expected to explain **why** your prompt/model design improved results (or failed to), supported by error analysis.

---

## 11) Error Analysis (Required)

Include qualitative and quantitative analysis of failures:
- False positives: what patterns caused over-flagging?
- False negatives: what misinformation styles were missed?
- Modality conflict cases: text says one thing, visuals suggest another
- Ambiguous/noisy cases and model uncertainty

Provide at least 8–10 representative examples with short commentary.

---

## 12) Project Timeline (4–6 weeks)

### Week 1
- Data setup, sampling, preprocessing checks
- Define baseline and evaluation scripts

### Week 2
- Train/run baseline, validate pipeline integrity
- Draft first MLLM prompt templates

### Week 3
- Prompt engineering iterations (few-shot, decomposition, structured output)
- Run val ablations and error analysis

### Week 4
- Finalize advanced system
- Run locked test evaluation

### Week 5/6
- Fine-tuning extension
- Additional robustness checks and final polishing

---

## 13) Submission Package

1. **Code repository** with:
   - data loading scripts
   - baseline code
   - advanced MLLM pipeline
   - prompt templates/configs
   - evaluation scripts

2. **Final report** (8–12 pages) including:
   - problem framing and related methods
   - baseline approach
   - advanced approach and prompt design
   - experimental setup and metrics
   - results table(s)
   - ablations
   - error analysis
   - limitations and future work

3. **Reproducibility appendix**:
   - environment details
   - model versions/APIs used
   - hardware usage
   - run commands

4. **Short presentation** (10–15 min):
   - key findings
   - what worked and what didn’t
   - lessons learned about MLLMs for misinformation detection

---

## 14) Grading Rubric

- **20%** Baseline correctness and rigor
- **30%** Advanced MLLM design + prompt engineering quality
- **20%** Experimental quality (ablations, fairness, reproducibility)
- **15%** Performance gains and interpretation
- **15%** Report clarity + presentation quality

---

## 15) Practical Notes

- Keep API costs in mind: cache model outputs and reuse intermediate artifacts.
- Build robust parsing for LLM outputs (JSON schema recommended).
- Add guardrails for malformed responses and retry logic.
- Track every experiment in a log table (prompt version, model, seed, metrics).

---

## 16) Minimum Success Criteria

To pass project requirements, your submission must include:
1. A working baseline with test metrics,
2. A working advanced MLLM system with prompt engineering,
3. A direct comparison showing whether and where the advanced method improves,
4. Reproducible code and clear documentation.

This project mirrors realistic research engineering workflows in multimodal misinformation detection.
