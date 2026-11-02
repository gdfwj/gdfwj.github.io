---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
layout: home
body_class: home-background
---

<section class="home-card home-about" markdown="1">
# About me

I am a PhD student in Computer Science at UC Irvine, advised by [Prof. Nalini Venkatasubramanian](https://ics.uci.edu/~dsm/members.html). I received my Master of Science in Computer Science from UC San Diego in June 2026, where I worked with [Prof. Tajana Šimunić Rosing](http://varys.ucsd.edu/people/) and mentor [Ye Tian](https://yetianucsd.github.io/) in [SEELab](https://seelab.ucsd.edu/) on IoT and edge AI.

My research focuses on distributed systems for edge LLM serving, resource-efficient inference, sensor-grounded reasoning, and privacy-aware and connectivity-resilient smart spaces. At UC Irvine, I am exploring distributed LLM serving across local edge devices and how sensing and contextual data can support locally grounded reasoning.

</section>

<section class="home-card" markdown="1">
## Education

{% include education.md %}
</section>

{% include home-news.html %}

<section class="home-card home-publications" markdown="1">
## Selected Publications

{% assign selected_publications = site.publications | where: "selected", true | sort: "date" | reverse %}
{% for post in selected_publications %}
{% include publication-summary.html %}
{% endfor %}

[View all publications →]({{ "/publications/" | relative_url }})
</section>

{% include visitor-map.html %}
