# HOPPER-G: Graph-Path Contexts for Small Language Models

> **Status:** research in progress (follow-up to [HOPPER](https://github.com/sungchul02/HOPPER)). Code will be released with the paper (공개 예정).

HOPPER-G is a training-free method that builds the input context for small language models (0.6B–4B parameters) in multi-hop question answering. It links retrieved documents into a graph (document A → document B when a sentence of A mentions the title of B), searches for an evidence path starting from the documents the question mentions, and gives the model the sentences on that path, either alone or together with the sentences selected by HOPPER. The goal is to keep the evidence while removing unrelated sentences that distract small models. Context construction runs on a CPU without any trained model.

**The code will be added when the paper is released.** It will include the context construction code, prompts, evaluation question IDs, model digests and run records.

---

HOPPER-G는 다중 홉 질의응답에서 소형 언어모델(6억∼40억 파라미터)의 입력 문맥을 구성하는, 학습이 필요 없는 방법이다. 검색 문서 사이에 제목 언급 관계로 그래프를 만들고, 질문이 언급한 문서에서 출발하는 근거 경로를 찾아 경로 위의 문장을 입력한다. 정답 근거는 유지하면서 소형 모델을 헷갈리게 하는 관련 없는 문장을 줄이는 것이 목표다. [HOPPER](https://github.com/sungchul02/HOPPER)의 후속 연구로 현재 진행 중이며, **코드는 논문 공개 시 이 저장소에 기재한다**.
