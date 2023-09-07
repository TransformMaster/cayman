---
layout: default
title: sescore2
description: Stratified Error Synthesis Score
---

# SESCORE2: Learning Text Generation Evaluation via Synthesizing Realistic Mistakes

SESCORE2, is a SSL method to train a metric for general text generation tasks without human ratings. We develop a technique to synthesize candidate sentences with varying levels of mistakes for training. To make these self-constructed samples realistic, we introduce retrieval augmented synthesis on anchor text; It outperforms SEScore in four text generation tasks with three languages (The overall kendall correlation improves 14.3%).

### Author Email: wendaxu@cs.ucsb.edu


### Install all dependencies:
```
pip install SEScore2
```


### Instructions to score sentences using SEScore2:

Currently, the PyPI version only support English Checkpoint. To run SEScore2 for text generation evaluation:


```python
from sescore2 import SEScore2

scorer = SEScore2('en') # Download and load in metric with specified language, en (English), de (German), ja ('Japanese')

refs = ["Jova becomes Western Hemisphere's strongest hurricane so far in 2023 ... for now", "Jova becomes Western Hemisphere's strongest hurricane so far in 2023 ... for now"]

outs = ["Jova set to become Western Hemisphere's most powerful hurricane in 2023...so far", "Jova set to become Western Hemisphere's weakest hurricane in 2023"]

scores_ls = scorer.score(refs, outs, 1)
```
