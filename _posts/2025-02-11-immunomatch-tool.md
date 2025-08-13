---
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: true
      share: true
      related: true
title: "ImmunoMatch learns antibody chain pairing"
header:
  teaser: /assets/images/immunomatch-tool.png
---

![image-center](/assets/images/immunomatch-tool.png){: .align-center}

[**ImmunoMatch**](https://github.com/Fraternalilab/ImmunoMatch/) is an machine learning framework built atop antibody‑specific language models to predict cognate heavy–light (H–L) chain pairs from single B‑cell data. We used this to study how chain pairing propensities change with B cell maturation, and explored the utility of ImmunoMatch in therapeutic antibody design. Fantastic work led by Dongjun!

Read the preprint on [bioRxiv](https://www.biorxiv.org/content/10.1101/2025.02.11.637677v1).
