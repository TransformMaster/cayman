---
layout: default
title: SEScore
description: Stratified Error Synthesis Score - Automatic Text Evaluation Metrics -
---


## About SEScore

Welcome to our project page, dedicated to our family of innovative reference-based text-generation evaluation metrics. 

### SEScore
*SEScore* is a reference-based text-generation evaluation metric that requires no pre-human-annotated error data, described in our paper [Not All Errors are Equal: Learning Text Generation Metrics using Stratified Error Synthesis.](https://arxiv.org/abs/2210.05035) from EMNLP 2022. Reader can refer [https://research.google/pubs/pub51897/](https://research.google/pubs/pub51897/) for our WMT22 results!

Its effectiveness over prior methods like BLEU, BERTScore, BARTScore, PRISM, COMET and BLEURT has been demonstrated on a diverse set of language generation tasks, including translation, captioning, and web text generation. and we are very excited to share it with you!

### SEScore2
Building upon the solid foundation laid by SEScore, we then introduced SEScore2. This unsupervised model further innovates by synthesizing realistic model mistakes through the perturbation of sentences retrieved from a corpus. A key strength of SEScore2 lies in its flexibility to be extended to numerous languages, while simultaneously offering trustworthy severity estimation. These advancements are detailed in our paper [SESCORE2: Learning Text Generation Evaluation via Synthesizing Realistic Mistake.](https://arxiv.org/abs/2212.09305).


### INSTRUCTSCORE (SEScore3)
Our latest addition to the family, INSTRUCTScore, is a manifestation of our commitment to providing open-source, explainable evaluation metrics for text generation. It exploits explicit human instruction and the vast implicit knowledge of GPT4, fine-tuning an LLAMA model to develop an evaluation metric capable of delivering a diagnostic report consistent with human judgment. These advancements are detailed in our paper [INSTRUCTSCORE: Towards Explainable Text Generation Evaluation with Automatic Feedback.](https://arxiv.org/pdf/2305.14282.pdf).

* * *

```bibtex
@inproceedings{xu-etal-2022-not,
  title={Not All Errors are Equal: Learning Text Generation Metrics using Stratified Error Synthesis},
  author={Xu, Wenda and Tuan, Yi-lin and Lu, Yujie and Saxon, Michael and Li, Lei and Wang, William Yang},
  booktitle ={Proceedings of the 2022 Conference on Empirical Methods in Natural Language Processing},
  month={dec},
  year={2022},
  url={https://arxiv.org/abs/2210.05035}
}
@article{xu2022sescore2,
  title={SEScore2: Retrieval Augmented Pretraining for Text Generation Evaluation},
  author={Xu, Wenda and Qian, Xian and Wang, Mingxuan and Li, Lei and Wang, William Yang},
  journal={arXiv preprint arXiv:2212.09305},
  year={2022}
}
@article{xu2023instructscore,
  title={Instructscore: Towards explainable text generation evaluation with automatic feedback},
  author={Xu, Wenda and Wang, Danqing and Pan, Liangming and Song, Zhenqiao and Freitag, Markus and Wang, William Yang and Li, Lei},
  journal={arXiv preprint arXiv:2305.14282},
  year={2023}
}
```

## Acknowledgements

The work of the [COMET](https://github.com/Unbabel/COMET) maintainers at [Unbabel](https://duckduckgo.com/?t=ffab&q=unbabel&ia=web) has been instrumental in producing SEScore.

