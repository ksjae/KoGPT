---
language: ko
tags:
- kogpt2
- gpt2
- text-generation
license: MIT
datasets:
- custom
metrics:
- none
---
**This model is no longer actively in training due to lack of computing resources. NIPA측의 정책 변경으로 고성능컴퓨팅 지원대상에서 제외됨에 따라, 모델 훈련을 더 이상 진행할 수 없게 되었습니다.**

# Model name
KoGPT2

<a href="https://www.buymeacoffee.com/ksjae" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1s5zZZL8j2waMTkwUOmSOv6IywoBrNm1z?usp=sharing)

Demo **NOT** available at : [아무말 대잔치](https://text.ksjit.com)

## Model description
GPT2 and GPT3 trained on ~40GB of Korean datasets.
see the included json files for hyperparameter details.

Available models (Training ATM):
- KoGPT2-base(117M)
- KoGPT2-medium(345M)
- KoGPT2-large(774M)
- KoGPT2-xlarge(1.5B)
- KoGPT2-2.7B *TBA*

Models are available as TF checkpoint files [Training script](https://github.com/ksjae/KoGPT2-train) or [Huggingface transformers](https://github.com/huggingface/transformers.git) compatible ones

n_ctx available : 1024 2048 384

## Intended uses & limitations
Intended for **Korean** text generation for ai-text-adventure(https://github.com/ksjae/ai-text-adventure) with PPLM.

### Downloads
Download files from links at the Releases tab.
Alternatively, it is available from [my own server(wget-friendly)](https://static.ksjit.com)

#### How to use

Try out on [colab](https://colab.research.google.com/drive/1s5zZZL8j2waMTkwUOmSOv6IywoBrNm1z?usp=sharing)

or go to [KoGPT2-train](https://github.com/ksjae/KoGPT2-train) and use scripts/demo.py 

#### Limitations and bias

v0.1 may have faulty tokenizers, producing bad outputs.

v0.2+ be GPT2 with n_ctx of 2048. True form of GPT-3 implementation(alternating layers) will not be available within the year.

If other limitations or errors are found, please open an issue.

## Training data

Initialized with GPT(774M,https://github.com/openai/gpt-2/blob/master/model_card.md).

The following data was used, and is available for redistribution [here](https://static.ksjit.com/datasets):

- Namuwiki database dump, Early 2020
- KCC(Kookmin University Corpus)
- Dump of Korean Wikipedia
- NAVER movie reviews
- Korean news(about 1GB) from Leipzig(a German university)
- Context data from KorSQUAD questions
- Parsed Korean CommonCrawl data(WIP)

Please note the completed dataset includes <|endoftext|> tags.

The following data were used, but is unavailable for redistribution:

- Sejong Corpus
- '모두의 말뭉치' from corpus.korean.go.kr
- A *PRIVATE* collection of korean novels
- Webcrawl of modern, uploaded text novels('텍본' - If you want to prevent your novel from going in the training set, please contact me and I will blacklist it)
- Game storylines (with authors' approval)


## Training procedure

All hyperparameters are the same as GPT2-large
One paragraph per line(TextDataset)

Early models(GPT2-large v0.2 and prior) are trained on 2xTesla V100 for 3~4 weeks.
Models up to XL size are trained on v3-8 TPUs.

## Eval results
> prompt >>> 나는 어두운 숲 속을 거닐고 있다.

### v0.1 (xl)
> 어느새 나는 그 작은 산들을 향해 뛰기 시작했다. 그리고 내 시야에는 이 골짜기에 대한 어떤 동경도, 혹은 동경과 환희조차 엿보였다가 사라졌다가는 사라져 버리고 말았 다. 그러나 나 역시 그것을 믿지 않았다. 아니 그것도 모른다……. 그렇다면 그것은 또 무슨 말인가? 내가 이렇게 말해도 좋을 텐데…… 하지만 어쨌든 이곳엔 왜 그리 먼 곳에서부터 찾아올까 하고 생각해 보았다. 그래서 그는 지금 어느 한 곳만을 헤매면서 자 꾸만 걸어오는 것일까?

### v0.2-WEB (xl)
> 나는 어두운 숲 속을 거닐고 있다. #앨리건트테이블 의 #코코넛젤리 색이 넘 예쁘고 맛나다. #그릭요거트 원물이 들어간 마지막  베이커리 #말차초코케이크 도 맛나고 겉에 초코도 두껍게 씹히고..✨💕💕👍🏻 . . #앨리건트테이블 @eleganttable_  #간식 #카페어니언베이커리베이커 #콩콩볼 #쿠키 #디저트맛집 #디저트카페 #dessert #카페스타그램 #맛스타그램 #먹스타 그램 #먹방 #일상 #daily

### v0.2-story (xl)
> 나는 어두운 숲 속을 거닐고 있다. 정명이 쓴웃음을 지은 채 곳에 걸어나왔다. ... ... ... ... 사망탑 높이까지 올라가야하나?


### BibTeX entry and citation info

```bibtex
@unpublished{CitekeyUnpublished,
      author = "Seungjae Kim",
      title  = "Introducing larger KoGPT2",
      year   = 2020
    }
```
