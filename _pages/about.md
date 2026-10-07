---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I am a PhD student in Computer Science at UC Irvine, advised by [Prof. Nalini Venkatasubramanian](https://nalini.ics.uci.edu/). I received my Master of Science in Computer Science from UC San Diego in June 2026, where I worked with [Prof. Tajana Šimunić Rosing](https://cseweb.ucsd.edu/~trosing/) and mentor [Ye Tian](https://yetianucsd.github.io/) in [SEELab](https://seelab.ucsd.edu/) on IoT and edge AI. I received my Bachelor of Engineering in Computer Science and Technology from Beihang University in June 2024.

My research focuses on distributed systems for edge LLM serving, resource-efficient inference, sensor-grounded reasoning, and privacy-aware and connectivity-resilient smart spaces. At UC Irvine, I am exploring distributed LLM serving across local edge devices and how sensing and contextual data can support locally grounded reasoning.

## CV

[View my CV]({{ '/cv/' | relative_url }}) · [Download CV (PDF)]({{ '/files/CV.pdf' | relative_url }})

## Education

{% include education.md %}

## News

- **September 2026:** I joined UC Irvine as a PhD student in Computer Science, advised by Prof. Nalini Venkatasubramanian.
- **2026:** LifeAgentBench was accepted to the EMNLP main conference.
- **June 2026:** I received my Master's in Computer Science from UC San Diego.
- **March 2026:** Our [KLDrive preprint](https://arxiv.org/abs/2603.21029) is available.
- **January 2026:** Our [LifeAgentBench preprint](https://arxiv.org/abs/2601.13880) is available, along with the [project code](https://github.com/gdfwj/LifeAgentBench).
- **2025:** Our paper [DailyLLM](https://arxiv.org/abs/2507.13737) appeared at IEEE MASS 2025.

## Selected Publications

{% assign selected_publications = site.publications | where: "selected", true | sort: "date" | reverse %}
{% for post in selected_publications %}
{% include publication-summary.html %}
{% endfor %}

[View all publications]({{ '/publications/' | relative_url }})
