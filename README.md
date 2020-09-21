---
language: ko
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
KoGPT3

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1s5zZZL8j2waMTkwUOmSOv6IywoBrNm1z?usp=sharing)
Demo available at : [아무말 대잔치](https://text.ksjit.com)

## Model description
GPT2 and GPT3 trained on ~40GB of Korean datasets.
see [Training data] for more details.

Available models (Training ATM):
- KoGPT3-base(117M)
- KoGPT3-medium(345M)
- KoGPT3-large(774M)
- KoGPT3-xlarge(1.5B)
- KoGPT3-2.7B
- KoGPT3-6.7B
- GPT3-13B if possible

## Intended uses & limitations
Intended for **Korean** text generation for ai-text-adventure(https://github.com/ksjae/ai-text-adventure) with PPLM.

### Downloads
Download files from links at the Releases tab.

#### How to use

from huggingface/transformers
```bash
python3 examples/text-generation/run_generation.py --model_type=gpt2 --model_name_or_path=kogpt2 --length=100 --fp16 --repetition_penalty=2 --p=0.8 --k=20
```

Or try out on [colab](https://colab.research.google.com/drive/1s5zZZL8j2waMTkwUOmSOv6IywoBrNm1z?usp=sharing)

#### Limitations and bias

If limitations or errors are found, please open an issue.

## Training data

Initialized with GPT(774M,https://github.com/openai/gpt-2/blob/master/model_card.md). Trained with the following data:
- Sejong Corpus
- Namuwiki database dump, Early 2020
- KCC(Kookmin University Corpus)
- Dump of Korean Wikipedia
- A *PRIVATE* collection of korean novels(with copyright cleared)
- Game storylines (with authors' approval)
- NAVER movie reviews
- Korean news(about 1GB) from a German university
- Context data from KorSQUAD questions
- '모두의 말뭉치' from corpus.korean.go.kr

## Training procedure

All hyperparameters are the same as GPT2-large
One paragraph per line(TextDataset)

Early models(GPT2-large v0.2 and prior) are trained on 2xTesla V100 for 3~4 weeks.
Some models are trained on v3-8 TPUs.
Larger models are trained on v3-128 TPUs.

## Eval results
> prompt >>> 나는 어두운 숲 속을 거닐고 있다.
> 어느새 나는 그 작은 산들을 향해 뛰기 시작했다. 그리고 내 시야에는 이 골짜기에 대한 어떤 동경도, 혹은 동경과 환희조차 엿보였다가 사라졌다가는 사라져 버리고 말았 다. 그러나 나 역시 그것을 믿지 않았다. 아니 그것도 모른다……. 그렇다면 그것은 또 무슨 말인가? 내가 이렇게 말해도 좋을 텐데…… 하지만 어쨌든 이곳엔 왜 그리 먼 곳에서부터 찾아올까 하고 생각해 보았다. 그래서 그는 지금 어느 한 곳만을 헤매면서 자 꾸만 걸어오는 것일까?


### BibTeX entry and citation info

```bibtex
@unpublished{CitekeyUnpublished,
      author = "Seungjae Kim",
      title  = "KoGPT2-large : A larger KoGPT2",
      year   = 2020
    }
```
