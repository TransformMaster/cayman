---
layout: default
title: SEScore
description: Stratified Error Synthesis Score
---
<em>This is the project page for EMNLP 2022 paper: “Not All Errors are Equal: Learning Text Generation Metrics using Stratified Error Synthesis”.</em>
## About SEScore

*SEScore* is a reference-based text-generation evaluation metric that requires no pre-human-annotated error data, described in our paper [Not All Errors are Equal: Learning Text Generation Metrics using Stratified Error Synthesis.](https://arxiv.org/abs/2210.05035) from EMNLP 2022. Reader can refer [https://research.google/pubs/pub51897/](https://research.google/pubs/pub51897/) for our WMT22 results!

Its effectiveness over prior methods like BLEU, BERTScore, BARTScore, PRISM, COMET and BLEURT has been demonstrated on a diverse set of language generation tasks, including translation, captioning, and web text generation. and we are very excited to share it with you!


#### Best unsupervised evaluation metric in WMT22 in all language pairs and domains!
* * *

## How to use SEScore

We hosted our SEScore metric and running instructions on HuggingFace: [https://huggingface.co/spaces/xu1998hz/sescore](https://huggingface.co/spaces/xu1998hz/sescore)

### Installation and usage
```
pip install -r requirements.txt
```

Minimal example (evaluating English text generation)
```python
import evaluate
sescore = evaluate.load("xu1998hz/sescore")
score = sescore.compute(
    references=['sescore is a simple but effective next-generation text evaluation metric'],
    predictions=['sescore is simple effective text evaluation metric for next generation']
)
}
```
*SEScore* compares a list of references (gold translation/generated output examples) with a same-length list of candidate generated samples. Currently, the output range is learned and scores are most useful in relative ranking scenarios rather than absolute comparisons. We are producing a series of rescaling options to make absolute SEScore-based scaling more effective.

### Available pre-trained models
Currently, the following language/model pairs are available:

| Language | pretrained data | pretrained model link |
|----------|-----------------|-----------------------|
| English  | MT              | [xu1998hz/sescore_english_mt](https://huggingface.co/xu1998hz/sescore_english_mt) |
| German   | MT              | [xu1998hz/sescore_german_mt](https://huggingface.co/xu1998hz/sescore_german_mt) |
| English  | webNLG17        | [xu1998hz/sescore_english_webnlg17](https://huggingface.co/xu1998hz/sescore_english_webnlg17) |
| English  | CoCo captions   | [xu1998hz/sescore_english_coco](https://huggingface.co/xu1998hz/sescore_english_coco) |

Please contact repo maintainer Wenda Xu to add your models!

## Limitations

*SEScore* is trained on synthetic data in-domain. 
Although this data is generated to simulate user-relevant errors like deletion and spurious insertion, it may be limited in its ability to simulate humanlike errors.
Model applicability is domain-specific (e.g., CoCo caption-trained model will be better for captioning than MT-trained).

We are in the process of producing and benchmarking general language-level *SEScore* variants.

## Citation

If you find our work useful, please cite the following:

```bibtex
@inproceedings{xu-etal-2022-not,
  title={Not All Errors are Equal: Learning Text Generation Metrics using Stratified Error Synthesis},
  author={Xu, Wenda and Tuan, Yi-lin and Lu, Yujie and Saxon, Michael and Li, Lei and Wang, William Yang},
  booktitle ={Proceedings of the 2022 Conference on Empirical Methods in Natural Language Processing},
  month={dec},
  year={2022},
  url={https://arxiv.org/abs/2210.05035}
}
```

## Acknowledgements

The work of the [COMET](https://github.com/Unbabel/COMET) maintainers at [Unbabel](https://duckduckgo.com/?t=ffab&q=unbabel&ia=web) has been instrumental in producing SEScore.

