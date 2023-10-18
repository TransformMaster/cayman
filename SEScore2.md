---
layout: default
title: SEScore2
description: Learning Text Generation Evaluation via Synthesizing Realistic Mistakes
---

SESCORE2, is a SSL method to train a metric for general text generation tasks without human ratings. We develop a technique to synthesize candidate sentences with varying levels of mistakes for training. To make these self-constructed samples realistic, we introduce retrieval augmented synthesis on anchor text; It outperforms SEScore in four text generation tasks with three languages (The overall kendall correlation improves 14.3%).

### Author Email: wendaxu@cs.ucsb.edu

## How to use SEScore
### Install all dependencies:
```
pip install SEScore2
```

### Instructions to score sentences using SEScore2:

Currently, the PyPI version only support English (en) and German (de) Checkpoint. The model checkpoint is trained using mT5-xl and using Human rating data to fine-tune.

To run SEScore2 for text generation evaluation:

```python
from sescore2 import SEScore2

scorer = SEScore2('en') # Download and load in metric with specified language, en (English), de (German), ja ('Japanese')

refs = ["Jova becomes Western Hemisphere's strongest hurricane so far in 2023 ... for now", "Jova becomes Western Hemisphere's strongest hurricane so far in 2023 ... for now"]

outs = ["Jova set to become Western Hemisphere's most powerful hurricane in 2023...so far", "Jova set to become Western Hemisphere's weakest hurricane in 2023"]

scores_ls = scorer.score(refs, outs, 1)
```

## GitHub Page

If you want to reproduce the synthetic data, and use the original XLM/RemBERT SEScore2 weight, please refer to the GitHub repository: https://github.com/xu1998hz/SEScore2

### Install all dependencies for GitHub version:

````
```
pip install -r requirement/requirements.txt

# To evaluate WMT shared metric task using official script
git clone https://github.com/google-research/mt-metrics-eval.git
cd mt-metrics-eval
pip install .

# Download evaluation data for WMT20, 21 and 22
alias mtme='python3 -m mt_metrics_eval.mtme'
mtme --download  # Puts ~1G of data into $HOME/.mt-metrics-eval.
```
````

### Score sentences using SEScore2 for GitHub version:

Download weights and data from Google Drive (https://drive.google.com/drive/folders/1I9oji2_rwvifuUSqO-59Fi_vIok_Wvq8?usp=sharing)
We support five languages: English, German, Spanish, Chinese and Japanese.

````
```
from SEScore2 import SEScore2
from train.regression import *

scorer = SEScore2('en') # load in metric with specified language, en (English), de (German), ja ('Japanese')

refs = ["SEScore is a simple but effective next generation text generation evaluation metric", "SEScore it really works"]

outs = ["SEScore is a simple effective text evaluation metric for next generation", "SEScore is not working"]

scores_ls = scorer.score(refs, outs, 1)
```

## Citation

If you find our work useful, please cite the following:

    @misc{xu2023sescore2,
          title={SESCORE2: Learning Text Generation Evaluation via Synthesizing Realistic Mistakes}, 
          author={Wenda Xu and Xian Qian and Mingxuan Wang and Lei Li and William Yang Wang},
          year={2023},
          eprint={2212.09305},
          archivePrefix={arXiv},
          primaryClass={cs.CL}
    }
