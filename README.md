---
language: ko
thumbnail: "url to a thumbnail used in social sharing"
tags:
- kogpt-2
- gpt2-large
- text-generation
license: MIT
datasets:
- array of dataset identifiers
metrics:
- array of metric identifiers
---

# Model name
KoGPT2-large

## Model description

You can embed local or remote images using `![](...)`

## Intended uses & limitations
Intended for text generation for ai-text-adventure(https://github.com/ksjae/ai-text-adventure) with PPLM.


#### How to use

```python
# You can include sample code which will be formatted
```

#### Limitations and bias

Provide examples of latent issues and potential remediations.

## Training data

Describe the data you used to train the model.
If you initialized it with pre-trained weights, add a link to the pre-trained model card or repository with description of the pre-training data.

Initialized with GPT2-large(774M,https://github.com/openai/gpt-2/blob/master/model_card.md). Trained with the following data:
- Sejong Corpus
- Namuwiki database dump, Early 2020
- KCC(Kookmin University Corpus)
- Dump of Korean Wikipedia
- A *PRIVATE* collection of korean novels(with copyright cleared)
- Game storylines (with authors' approval)
- NAVER movie reviews
- Korean news(about 1GB) from a German university
- Context data from KorSQUAD questions

## Training procedure

All hyperparameters are the same as GPT2-large
One paragraph per line(TextDataset)

Trained on 2x Tesla V100(SXM2 32GB) for weeks

## Eval results
TBA

### BibTeX entry and citation info

```bibtex
@inproceedings{...,
  year={2020}
}
```
