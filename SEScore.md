---
layout: default
title: sescore
description: Stratified Error Synthesis Score
---
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

    @misc{xu2022errors,
          title={Not All Errors are Equal: Learning Text Generation Metrics using Stratified Error Synthesis}, 
          author={Wenda Xu and Yilin Tuan and Yujie Lu and Michael Saxon and Lei Li and William Yang Wang},
          year={2022},
          eprint={2210.05035},
          archivePrefix={arXiv},
          primaryClass={cs.CL}
    }
