---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

[Download CV (PDF)]({{ '/files/CV.pdf' | relative_url }})

## Education

{% include education.md %}

- **UC San Diego GPA:** 3.91/4.00. Key courses: Systems for LLMs and AI Agents, Differentiable Programming (A+), ML: Learning Algorithms (A+).
- **Beihang University GPA:** 3.92/4.0 (WES).

## Research Interests

Distributed systems for edge LLM serving; resource-efficient inference; sensor-grounded reasoning; privacy-aware and connectivity-resilient smart spaces.

## Scholarships & Awards

- **2021, 2022, 2023:** Academic Merit Scholarship, for outstanding undergraduate GPA.
- **2022, 2023:** Academic Competition Scholarship, for outstanding rankings in national or university-level discipline competitions.

{% include publication-list.md %}

## Research Experience

### Distributed LLM Serving in Pure-Edge Smart Spaces

**September 2026–Present** · Doctoral Research, University of California, Irvine. Advisor: Nalini Venkatasubramanian.

- Defining research questions for distributed LLM serving across local edge devices without relying on cloud inference.
- Studying how LLM services can incorporate sensor and contextual data from the surrounding physical space to support locally grounded reasoning.
- Targeting privacy-sensitive and intermittently connected smart spaces, with potential applications in homes, care environments, and remote monitoring sites.

### LifeAgentBench: Lifestyle Reasoning Benchmark

**July 2025–September 2025** · Research Assistant, System Energy Efficiency Lab, UC San Diego. Advisors: Ye Tian and Tajana Rosing.

- Built a benchmark of 22,573 questions spanning single-domain retrieval to long-horizon, cross-dimensional reasoning over structured lifestyle health records.
- Built automated evaluation pipelines for context-based reasoning and schema-to-SQL execution; the latest study evaluates 13 LLMs.
- Implemented LifeAgent, a training-free reasoning baseline using question decomposition, iterative retrieval, and deterministic computation.
- The paper reports 40.16% average accuracy on challenging subsets with Qwen2.5-7B, versus 7.74% for Context Prompting and 9.43% for Database-augmented Prompting.
- Released [code](https://github.com/gdfwj/LifeAgentBench) and the [manuscript](https://arxiv.org/abs/2601.13880).

### DailyLLM: Multimodal Activity Log Generation

**January 2025–April 2025** · Research Assistant, System Energy Efficiency Lab, UC San Diego. Advisors: Ye Tian and Tajana Rosing.

- Developed a lightweight LLM system for context-aware activity log generation and summarization from smartphone and smartwatch sensors.
- Organized IMU-based datasets, including preprocessing, augmentation, and data construction for model training.
- Built multi-task LoRA fine-tuning and evaluation pipelines to balance model capability and system efficiency.
- Deployed and evaluated the system on Raspberry Pi, resolving a quantized-kernel compatibility issue by selecting a supported bit-width. The paper reports four minutes to summarize a two-hour activity window on Raspberry Pi 5.
- Released [code and data](https://github.com/gdfwj/DailyLLM) and a [project website](https://gdfwj.github.io/DailyLLM/); the paper was accepted to IEEE MASS 2025.

### Reconstruction of Perceived Face Images from fMRI

**April 2023–December 2023** · Research Assistant, Medical-Engineering Innovation Research Institute. Advisor: Hui Zhang.

- Developed a GAN pipeline to reconstruct face stimulus images from fMRI signals.
- Proposed CelebA pretraining with VGGFace feature conditioning to mitigate limited paired fMRI-image data.
- Designed a double-flow discriminator to improve reconstruction fidelity.
- Released the [manuscript](https://arxiv.org/abs/2312.07478) on arXiv.

## Service

{% include service.md %}
